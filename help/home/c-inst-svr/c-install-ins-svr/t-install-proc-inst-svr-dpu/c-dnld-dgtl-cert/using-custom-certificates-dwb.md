---
description: Instruktioner för hur du använder anpassade certifikat.
title: Använda anpassade certifikat i Data Workbench
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Använda anpassade certifikat i Data Workbench{#using-custom-certificates-in-data-workbench}

Instruktioner för hur du använder anpassade certifikat.

Ett certifikat som används av Data Workbench-klienten eller servern måste signeras av en betrodd certifikatutfärdare (Certificate Authority). Data Workbench-kunder får certifikat som är signerade av Visual Sciences CA. Dessa certifikat är betrodda av Data Workbench-programmet, eftersom [!DNL trust_ca_cert.pem] (som tillhandahålls tillsammans med Insight-programmet och lagras i **certifikatkatalogen** för både servrar och klienter) innehåller ett *rotcertifikatutfärdarcertifikat* för Visual Sciences CA. Dessa certifikat används både för licensiering av programvaran och autentisering när klienter och servrar kommunicerar med varandra med SSL. Endast certifikat som utfärdats av Visual Sciences CA kan användas för licensiering, men andra certifikat kan användas för kommunikation och autentisering. Certifikat som utfärdats av andra certifikatutfärdare än Visual Sciences kallas nedan *anpassade certifikat.*

**Viktigt:** För servrar och klienter använder Data Workbench de certifikatfiler som är installerade i klientens eller serverns **certifikatkatalog** eller certifikat som uttryckligen identifieras i dess konfiguration. Du kan även använda [Windows certifikatarkiv](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) för klienter.

Följande instruktioner beskriver de procedurer som ska följas för att använda anpassade certifikat för kommunikation mellan Data Workbench-klienter och -servrar. Alla detaljer är inte ett svårt krav och olika processvariationer kan användas. Anvisningarna nedan har dock testats så att de fungerar.

## Konfigurera anpassade klientcertifikat {#section-2083fd41973e451fa404e7a4ae4da591}

1. Lägg till certifikatet för den utfärdande certifikatutfärdaren i [!DNL trust_cert_ca.pem], som är installerat i **certifikatkatalogen** för klienten och certifikatet för alla servrar i varje kluster som ska användas med det här anpassade certifikatet.

1. Hämta ett anpassat certifikat för varje server i klustret med följande villkor:

   1. Certifikatet är formaterat som ett [!DNL .pem] certifikat.
   1. Certifikatet innehåller dess nyckel och är okrypterat (det har alltså ingen lösenord/lösenordsfras).

      Ett certifikat innehåller en nyckel med en av följande rader:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Ett sätt att ta bort lösenordsfrasen från ett [!DNL .pem] certifikat:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Certifikatet har CN, O, OU osv. som krävs för den här klienten i serverns [!DNL Access Control.cfg] fil.
   1. Certifikatet utfärdades i *syfte **** av *klienten* (eller både *server* **och** *klient*).

      Följande kommandon kan användas för att verifiera att ett certifikat har en avsedd kod som server och/eller klient:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      För ett servercertifikat bör båda kommandona ge:

      ```
      custom_communications_cert.pem: OK
      ```

      För ett klientcertifikat krävs bara det andra kommandot för att ge det [!DNL OK].

1. Placera certifikatet i klientens **certifikatkatalog** .
1. Kontrollera [!DNL Insight.cfg] under *serverInfo* för varje kluster som du vill använda det här certifikatet att det *anpassade klientcertifikatet* har ett namn, till exempel:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## Konfigurera anpassade servercertifikat {#setting-up-custom-server-certificates}

I det här avsnittet förutsätts att du har ett kluster som körs med certifikat som utfärdats av Visual Sciences och att konfigurationen följer vanliga rutiner (som katalogen *Komponenter för att bearbeta servrar* på huvudservern synkroniseras med *komponentkatalogerna* för alla DPU:er).

1. Lägg till certifikatet för den utfärdande certifikatutfärdaren till den [!DNL trust_cert_ca.pem] som är installerad på alla servrar i klustret och alla klienter som behöver kommunicera med det här klustret.
1. Skaffa ett anpassat certifikat för varje server i klustret med följande krav:

   1. Anpassat certifikat är formaterat som ett [!DNL .pem] certifikat.
   1. Certifikatet innehåller dess nyckel och är okrypterat (det har alltså ingen lösenord/lösenordsfras).

      Ett certifikat innehåller en nyckel om det har en rad som:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Ett sätt att ta bort lösenordsfrasen från ett [!DNL .pem] certifikat:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Certifikatet har samma CN som den [!DNL server_cert.pem] som är installerad på servern.
   1. Certifikatet utfärdades i syfte att *skapa server* och *klient*.

      Följande kommandon kan användas för att verifiera att ett certifikat har en avsedd kod som server och/eller klient:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      För ett servercertifikat bör båda kommandona ge:

      ```
      custom_communications_cert.pem: OK
      ```

      För ett klientcertifikat krävs bara det andra kommandot för att ge det [!DNL OK].

1. Installera varje servers anpassade certifikat i **certifikatkatalogen** på servern som [!DNL custom_communications_cert.pem].

1. Med en textredigerare lägger du till följande rad i **filen Communications.cfg** i både *Components* och *Components för att bearbeta serverkataloger* , direkt under den första raden ([!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Starta om alla servrar.

**Om certifikatfelsvarning**

När Insight-servern eller -klienten söker efter ett **licenscertifikat** i **certifikatkatalogen** försöker den validera alla certifikat (utom [!DNL trust_ca_cert.pem]) mot en hårdkodad kopia av Insight CA-certifikatet, som inte kan validera något anpassat certifikat i katalogen. Servern utfärdar den här varningen:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Den här varningen kan ignoreras.
