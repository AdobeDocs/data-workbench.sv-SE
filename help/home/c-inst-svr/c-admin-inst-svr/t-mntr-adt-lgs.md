---
description: Granskningsloggfiler spårar alla anslutningsförsök till och frånkopplingar från Insight Server, som alla är loggade i <YYYMMDD>-access.txt-filerna som finns som standard i Granskningsmappen i Insight Server-installationskatalogen.
solution: Insight
title: Övervaka granskningsloggar
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Övervaka granskningsloggar{#monitoring-audit-logs}

Granskningsloggfiler spårar alla anslutningsförsök till och frånkopplingar från Insight Server, som alla är loggade i de filer som finns som standard i mappen Audit i installationskatalogen för Insight Server. `<YYYYMMDD>-access.txt`

**Rekommenderad frekvens:** Dagligen eller vid behov för felsökning

Granskningsloggar kan vara mycket användbara vid felsökning av problem som uppstår vid anslutning till [!DNL Insight Server]. Du kan övervaka dessa loggar med hjälp av det automatiska hanteringsverktyget eller genom att visa [!DNL access.txt] filerna direkt.

**Så här visar du access.txt-filer via[!DNL Server Files Manager]**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för en aktiv bild [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Audit]** att visa innehållet.
1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* bredvid önskad fil och klicka på **[!UICONTROL Make Local]**. En bock visas bredvid filnamnet i [!DNL Temp] kolumnen.
1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Granskningsloggen visas i ett nytt fönster i Microsoft Windows Anteckningar.

   ![Steginformation](assets/cfg_accesscontrol_accessFile.png)

