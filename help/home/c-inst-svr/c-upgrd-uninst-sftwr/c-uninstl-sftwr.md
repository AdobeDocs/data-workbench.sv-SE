---
description: Instruktioner för att avinstallera Insight Server, Transform eller Repeater.
solution: Analytics
title: Avinstallerar programvaran
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---


# Avinstallerar programvaran{#uninstalling-your-software}

Instruktioner för att avinstallera Insight Server, Transform eller Repeater.

## Avinstallerar Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. Avregistrera tjänsten [!DNL Insight Server] Windows.

   1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade [!DNL Insight Server].

      Exempel: [!DNL C:\Adobe\Server\bin]

   1. Kör följande kommando i kommandotolken för att stoppa och avregistrera den som en tjänst i Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Ta bort [!DNL Insight Server] installationskatalogen.

## Transformering avinstalleras {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Följ de här stegen för att uppdatera [!DNL profile.cfg] filen för varje profil som du använde [!DNL Transform].

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret [!DNL profile.cfg] visas.

   1. I [!DNL profile.cfg] fönstret tar du bort [!DNL Transform] profilposten från katalogvektorn.

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. Högerklicka [!DNL Profile Manager]på bockmarkeringen för [!DNL profile.cfg] i [!DNL User] kolumnen och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Ta bort [!DNL Transform] mappen från [!DNL Profiles] mappen i din [!DNL Insight Server] installationskatalog.

## Avinstallerar Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Avregistrera tjänsten [!DNL Repeater] Windows.

   1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade [!DNL Repeater].

      Exempel: [!DNL D:\Adobe\Repeater\bin]

   1. Kör följande kommando i kommandotolken för att stoppa och avregistrera den som en tjänst i Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Ta bort [!DNL Repeater] installationskatalogen.

