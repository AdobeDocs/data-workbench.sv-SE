---
description: Steg för att hämta och installera det digitala certifikatet.
solution: Analytics
title: Installationsprocedurer för digitalt certifikat
topic: Data workbench
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installationsprocedurer för digitalt certifikat{#digital-certificate-installation-procedures}

Steg för att hämta och installera det digitala certifikatet.

1. Öppna webbläsaren och gå till [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Din webbläsare kan uppmana dig att presentera ett digitalt certifikat just nu. Om så är fallet klickar du bara på **[!UICONTROL Cancel]** för att stänga dialogrutan.

1. På inloggningsskärmen anger du kontonamnet och lösenordet som du fick från Adobe och klickar sedan på **[!UICONTROL login]**.
1. Leta reda på certifikatet som har utfärdats för din instans av [!DNL Report] servern (*ditt namn*.pem) och klicka på ![](assets/btn_save_certificatedownload.PNG) ikonen som är kopplad till certifikatet.
1. När du uppmanas att spara certifikatet klickar du på **[!UICONTROL Save]**.
1. Hämta filen till certifikatmappen i den katalog där du installerade [!DNL Report Server].

   Den här mappen innehåller redan en certifikatfil med namnet [!DNL trust_ca_cert.pem]. Båda certifikatfilerna måste alltid finnas för att [!DNL Report] Server ska fungera.

