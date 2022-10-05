---
description: En snabbguide för hur du konfigurerar ett Query API.
title: Inställningar för fråge-API
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
exl-id: 8b9dace8-4dad-434c-aec3-2f6ca872a5f6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Inställningar för fråge-API{#query-api-setup}

{{eol}}

En snabbguide för hur du konfigurerar ett Query API.

Följ stegen nedan för att konfigurera Query API:

1. Hämta API-certifikatanskaffning

   Skicka ett e-postmeddelande till Tech Ops Team of Adobe - `Dataworkbench@adobe.com`.

   Ange det CN-namn som du vill använda för fråge-API( anger ett generiskt namn som `<Client>` Fråga-API).

   >[!NOTE]
   >
   >Tech Ops genererar certifikatet och överför det till en URL. Meddela Adobe Consultants när Tech Ops har fått ett meddelande om att biljetten har genererats, så att de kan skicka tillbaka biljetten till dig.

1. Hämtar och extraherar API-tratten. Ta emot en api-stunnel-fil från din konsult.

   Kontrollera att Perl är installerat på datorn.

   I den extraherade mappen (mappsökvägen där du kopierar filen) kopierar du ditt Query API-certifikat inuti *stunnel* mapp.

1. Konfigurera Stunnel.conf

   Det ska finnas en fil som heter *stunnel.conf* inuti *Tunnel* mapp (där du kopierade ditt certifikat).

   Redigera filen i Anteckningar.

   ![](assets/dwb_impl_API1.png)

   Ändra parametrarna enligt följande: ![](assets/dwb_impl_API2.png)

   Två parametrar måste ändras i den här filen.

   * *Certifikat* = Namnet på ditt certifikat. I det här exemplet är det Aadhithiya Ramani QAPI Client.pem.
   * *Anslut* =Servernamnet för DPU:n.

1. Kopierar *Query.pm*.

   The *Query.pm* -filen kommer att vara tillgänglig i API-mappen för Insight.

   Kopiera *Query.pm* och klistra in den i mappen Perl Library (vanligtvis *C:\Perl64\lib *, men kontrollera var Perl är installerad i datorn).

1. Ändra *api-http.pl* fil

   Filen api-http.pl är tillgänglig i mappen api-stunnel.

   Endast en parameter som ska ändras

   *Min $-profil* = Profilnamnet som du konfigurerar fråge-API:t för.

1. Installera fråge-API:t.

   Öppna kommandotolken som &quot;Administratör&quot; i systemet och gå till den katalog där du extraherade filen *stunnel* som visas: ![](assets/dwb_impl_API3.png)

   Kör följande kommando *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   När kommandot har körts visas ett fönster som anger att *stunnel* är installerat.

   >[!NOTE]
   >
   >När kommandot har körts visas ett fönster som anger att *stunnel* är installerat.

1. Testa Query API-instanskonfigurationen

   Det sista steget i den här processen är att testa konfigurationen av Query API. I kommandotolken som du använde för att installera katalogen api-stunnel. ![](assets/dwb_impl_API5.png)

   Kör Perl-skriptet som finns i mappen med följande kommando* perl api-http.pl*. ![](assets/dwb_impl_API6.png)

   När du har kört skriptet ska resultatet se ut som skärmbilden nedan (datum- och resultatvärdena varierar beroende på tidpunkten och andra parametrar i profilen som du har konfigurerat Query API (i steg 6). ![](assets/dwb_impl_API7.png)
