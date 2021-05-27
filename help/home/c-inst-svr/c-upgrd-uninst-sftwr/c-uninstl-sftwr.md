---
description: Instruktioner för att avinstallera Insight Server, Transform eller Repeater.
title: Avinstallerar programvaran
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Avinstallerar din programvara{#uninstalling-your-software}

Instruktioner för att avinstallera Insight Server, Transform eller Repeater.

## Avinstallerar Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Avregistrera Windows-tjänsten [!DNL Insight Server].

   1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade [!DNL Insight Server].

      Exempel: [!DNL C:\Adobe\Server\bin]

   1. Kör följande kommando i kommandotolken för att stoppa och avregistrera den som en tjänst i Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Ta bort installationskatalogen för [!DNL Insight Server].

## Avinstallerar Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Följ de här stegen för att uppdatera [!DNL profile.cfg]-filen för varje profil som du använde [!DNL Transform] för.

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret [!DNL profile.cfg] visas.

   1. I fönstret [!DNL profile.cfg] tar du bort profilposten [!DNL Transform] från katalogvektorn.

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager] högerklickar du på bockmarkeringen för [!DNL profile.cfg] i kolumnen [!DNL User] och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Ta bort mappen [!DNL Transform] från mappen [!DNL Profiles] i installationskatalogen för [!DNL Insight Server].

## Avinstallerar repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Avregistrera Windows-tjänsten [!DNL Repeater].

   1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade [!DNL Repeater].

      Exempel: [!DNL D:\Adobe\Repeater\bin]

   1. Kör följande kommando i kommandotolken för att stoppa och avregistrera den som en tjänst i Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Ta bort installationskatalogen för [!DNL Repeater].
