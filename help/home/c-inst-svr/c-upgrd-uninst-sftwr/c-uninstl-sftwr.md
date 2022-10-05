---
description: Instruktioner för att avinstallera Insight Server, Transform eller Repeater.
title: Avinstallerar programvaran
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Avinstallerar programvaran{#uninstalling-your-software}

{{eol}}

Instruktioner för att avinstallera Insight Server, Transform eller Repeater.

## Avinstallerar Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Avregistrera [!DNL Insight Server] Windows-tjänst.

   1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade [!DNL Insight Server].

      Exempel: [!DNL C:\Adobe\Server\bin]

   1. Kör följande kommando i kommandotolken för att stoppa och avregistrera den som en tjänst i Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Ta bort [!DNL Insight Server] installationskatalog.

## Transformering avinstalleras {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Använd följande steg för att uppdatera [!DNL profile.cfg] för varje profil som du använder [!DNL Transform].

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. The [!DNL profile.cfg] visas.

   1. I [!DNL profile.cfg] fönster, ta bort [!DNL Transform] Profilpost från katalogvektorn.

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager], högerklicka på bockmarkeringen för [!DNL profile.cfg] i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Ta bort [!DNL Transform] mapp från [!DNL Profiles] i din [!DNL Insight Server] installationskatalog.

## Avinstallerar Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Avregistrera [!DNL Repeater] Windows-tjänst.

   1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade [!DNL Repeater].

      Exempel: [!DNL D:\Adobe\Repeater\bin]

   1. Kör följande kommando i kommandotolken för att stoppa och avregistrera den som en tjänst i Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Ta bort [!DNL Repeater] installationskatalog.
