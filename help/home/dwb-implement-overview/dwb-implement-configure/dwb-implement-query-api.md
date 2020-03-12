---
description: En snabbguide för hur du konfigurerar ett Query API.
title: Inställningar för fråge-API
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Inställningar för fråge-API{#query-api-setup}

En snabbguide för hur du konfigurerar ett Query API.

Följ stegen nedan för att konfigurera Query API:

1. Hämta API-certifikatanskaffning

   Skicka ett e-postmeddelande till Tech Ops Team of Adobe Email - `Dataworkbench@adobe.com`.

   Ange det CN-namn som du vill använda för fråge-API( ange ett generiskt namn som `<Client>` Query API).

   >[!NOTE]
   >
   >Tech Ops genererar certifikatet och överför det till en URL. Meddela Adobe Consultants när Tech Ops har fått ett meddelande om att biljetten har genererats, så att de får tillbaka biljetten.

1. Hämtar och extraherar API-tratten. Ta emot en api-stunnel-fil från din konsult.

   Kontrollera att Perl är installerat på datorn.

   I den extraherade mappen (den mappsökväg där du kopierar filen) kopierar du ditt Query API-certifikat inuti *mappen* .

1. Konfigurera Stunnel.conf

   Det ska finnas en fil med namnet *stunnel.conf* i mappen *Stunnel* (där du kopierade ditt certifikat).

   Redigera filen i Anteckningar.

   ![](assets/dwb_impl_API1.png)

   Ändra parametrarna enligt följande: ![](assets/dwb_impl_API2.png)

   Två parametrar måste ändras i den här filen.

   * *Certifikat* = Namnet på certifikatet. I det här exemplet är det Aadhithiya Ramani QAPI Client.pem.
   * *Connect* =Servernamnet för DPU:n.

1. Kopierar *Query.pm*.

   Filen *Query.pm* är tillgänglig i API-mappen för Insight.

   Kopiera filen *Query.pm* och klistra in den i mappen Perl Library (vanligtvis *C:\Perl64\lib *, men kontrollera var Perl är installerad i datorn).

1. Ändra filen *api-http.pl*

   Filen api-http.pl är tillgänglig i mappen api-stunnel.

   Endast en parameter som ska ändras

   *Min $profile* = Profilnamnet som du konfigurerar Query API för.

1. Installera fråge-API:t.

   Öppna kommandotolken i systemet som &quot;Administratör&quot; och navigera till den katalog där du extraherade *stunnel* enligt följande: ![](assets/dwb_impl_API3.png)

   Kör följande kommando *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   När kommandot har utförts visas ett fönster som anger att *bedövningen* är installerad.

   >[!NOTE]
   >
   >När kommandot har utförts visas ett fönster som anger att *bedövningen* är installerad.

1. Testa Query API-instanskonfigurationen

   Det sista steget i den här processen är att testa konfigurationen av Query API. I kommandotolken som du använde för att installera katalogen api-stunnel. ![](assets/dwb_impl_API5.png)

   Kör Perl-skriptet som finns i mappen med följande kommando* perl api-http.pl*. ![](assets/dwb_impl_API6.png)

   När du har kört skriptet ska resultatet se ut som skärmbilden nedan (datum- och resultatvärdena varierar beroende på tidpunkten och andra parametrar i profilen som du har konfigurerat Query API (i steg 6). ![](assets/dwb_impl_API7.png)
