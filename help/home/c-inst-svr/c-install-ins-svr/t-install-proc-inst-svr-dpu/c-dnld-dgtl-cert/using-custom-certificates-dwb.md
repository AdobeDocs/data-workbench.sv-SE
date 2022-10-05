---
description: Instruktioner för hur du använder anpassade certifikat.
title: Använda anpassade certifikat i Datan Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
exl-id: f813d599-723f-4b5d-a0b5-f4d71c1b1a22
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 0%

---

# Använda anpassade certifikat i Datan Workbench{#using-custom-certificates-in-data-workbench}

{{eol}}

Instruktioner för hur du använder anpassade certifikat.

Ett certifikat som används av antingen Datans Workbench klient eller server måste signeras av en betrodd certifikatutfärdare (Certificate Authority). Data Workbench får certifikat som signerats av Visual Sciences CA. Dessa certifikat är betrodda av Datan Workbench eftersom [!DNL trust_ca_cert.pem] (medföljer programmet Insight och lagras i **Certifikat** katalogen på både servrar och klienter) innehåller en *Certifikat för rotcertifikatutfärdare* för Visual Sciences CA. Dessa certifikat används både för licensiering av programvaran och autentisering när klienter och servrar kommunicerar med varandra med SSL. Endast certifikat som utfärdas av Visual Sciences CA kan användas för licensiering, men andra certifikat kan användas för kommunikation och autentisering. Certifikat som utfärdats av andra certifikatutfärdare än Visual Sciences kallas nedan *anpassade certifikat.*

**Viktigt:** För servrar och klienter använder Datan Workbench de certifikatfiler som är installerade i klienten eller serverns **Certifikat** katalog eller certifikat som uttryckligen identifieras i konfigurationen. Du kan dock även använda [Windows certifikatarkiv](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) för kunder.

Följande instruktioner beskriver de procedurer som ska följas för att använda anpassade certifikat för kommunikation mellan Datans Workbench klienter och servrar. Alla detaljer är inte ett svårt krav och olika processvariationer kan användas. Anvisningarna nedan har dock testats så att de fungerar.

## Konfigurera anpassade klientcertifikat {#section-2083fd41973e451fa404e7a4ae4da591}

1. Lägg till certifikatet för den utfärdande certifikatutfärdaren i [!DNL trust_cert_ca.pem], som installeras i **Certifikat** klientens katalog och katalogen för alla servrar i varje kluster som ska användas med det här anpassade certifikatet.

1. Hämta ett anpassat certifikat för varje server i klustret med följande villkor:

   1. Certifikatet är formaterat som ett [!DNL .pem] certifikat.
   1. Certifikatet innehåller dess nyckel och är okrypterat (det har alltså ingen lösenord/lösenordsfras).

      Ett certifikat innehåller en nyckel med en av följande rader:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Ett sätt att ta bort lösenordsfrasen från en [!DNL .pem] certifikat:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Certifikatet har CN, O, OU osv. som krävs för den här klienten i serverns [!DNL Access Control.cfg] -fil.
   1. Certifikatet har utfärdats med en *syfte&#42;&#42;&#42;* av *klient* (eller båda *server* **och** *klient*).

      Följande kommandon kan användas för att verifiera att ett certifikat har en avsedd kod som server och/eller klient:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      För ett servercertifikat bör båda kommandona ge:

      ```
      custom_communications_cert.pem: OK
      ```

      För ett klientcertifikat krävs bara det andra kommandot för att ge [!DNL OK].

1. Placera certifikatet i klientens **Certifikat** katalog.
1. I [!DNL Insight.cfg] under *serverInfo* för varje kluster som du vill använda det här certifikatet måste du kontrollera att *kundcertifikat* har ett namn, till exempel:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Konfigurera anpassade servercertifikat {#setting-up-custom-server-certificates}

I det här avsnittet förutsätts att du har ett kluster som körs med certifikat som utfärdas av Visual Sciences och att konfigurationen följer vanliga rutiner (till exempel *Komponenter för serverbearbetning* katalogen på överordnad synkroniseras med *Komponenter* kataloger för alla DPU:er).

1. Lägg till certifikatet för den utfärdande certifikatutfärdaren i [!DNL trust_cert_ca.pem] som är installerat på alla servrar i klustret och alla klienter som behöver kommunicera med det här klustret.
1. Skaffa ett anpassat certifikat för varje server i klustret med följande krav:

   1. Anpassat certifikat är formaterat som [!DNL .pem] certifikat.
   1. Certifikatet innehåller dess nyckel och är okrypterat (det har alltså ingen lösenord/lösenordsfras).

      Ett certifikat innehåller en nyckel om det har en rad som:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Ett sätt att ta bort lösenordsfrasen från en [!DNL .pem] certifikat:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Certifikatet har samma CN som [!DNL server_cert.pem] som är installerat på servern.
   1. Certifikatet utfärdades i syfte att *server* och *klient*.

      Följande kommandon kan användas för att verifiera att ett certifikat har en avsedd kod som server och/eller klient:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      För ett servercertifikat bör båda kommandona ge:

      ```
      custom_communications_cert.pem: OK
      ```

      För ett klientcertifikat krävs bara det andra kommandot för att ge [!DNL OK].

1. Installera varje servers anpassade certifikat i **Certifikat** serverns katalog som [!DNL custom_communications_cert.pem].

1. Lägg till följande rad i en textredigerare: **Communications.cfg** i båda *Komponenter* och *Komponenter för serverbearbetning* kataloger, direkt under första raden ([!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Starta om alla servrar.

**Om certifikatfelsvarning**

När Insight-servern eller klienten letar efter en **licens** certifikatet i **Certifikat** katalogen försöker validera alla certifikat (förutom [!DNL trust_ca_cert.pem]), mot en hårdkodad kopia av Insight CA-certifikatet, som inte kan användas på något anpassat certifikat i katalogen. Servern utfärdar den här varningen:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Den här varningen kan ignoreras.
