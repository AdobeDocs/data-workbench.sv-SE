---
description: Steg för att hämta och installera det digitala certifikatet.
title: Installationsprocedurer för digitalt certifikat
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 0%

---

# Installationsprocedurer för digitalt certifikat{#digital-certificate-installation-procedures}

Steg för att hämta och installera det digitala certifikatet.

1. Öppna webbläsaren i [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Din webbläsare kan uppmana dig att presentera ett digitalt certifikat just nu. Om den gör det klickar du bara på **[!UICONTROL Cancel]** för att stänga dialogrutan.

1. På inloggningsskärmen anger du kontonamnet och lösenordet som du fick från Adobe och klickar sedan på **[!UICONTROL login]**.
1. Leta reda på certifikatet som har utfärdats för din instans av [!DNL Report] Server (*Ditt namn*.pem) och klicka på ikonen ![](assets/btn_save_certificatedownload.PNG) som är kopplad till certifikatet.
1. När du uppmanas att spara certifikatet klickar du på **[!UICONTROL Save]**.
1. Hämta filen till certifikatmappen i den katalog där du installerade [!DNL Report Server].

   Den här mappen innehåller redan en certifikatfil med namnet [!DNL trust_ca_cert.pem]. Båda certifikatfilerna måste alltid finnas för att [!DNL Report]-servern ska fungera.
