---
description: Granskningsloggfiler spårar alla anslutningsförsök till och frånkopplingar från Insight Server, som var och en är inloggad i <yyyymmdd>-access.txt-filer som finns som standard i mappen Audit i installationskatalogen för Insight Server.
title: Övervaka granskningsloggar
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---

# Övervaka granskningsloggar{#monitoring-audit-logs}

{{eol}}

Granskningsloggfiler spårar alla anslutningsförsök till och frånkopplingar från Insight Server, som var och en är inloggad i `<YYYYMMDD>-access.txt` filer som finns som standard i mappen Audit i installationskatalogen för Insight Server.

**Rekommenderad frekvens:** Dagligen eller vid behov för felsökning

Granskningsloggar kan vara mycket användbara vid felsökning av problem med anslutning till [!DNL Insight Server]. Du kan övervaka loggarna med hjälp av det automatiska hanteringsverktyget eller genom att visa [!DNL access.txt] filer direkt.

**Så här visar du access.txt-filer via[!DNL Server Files Manager]**

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för en aktiv [!DNL Insight Server] och klicka **[!UICONTROL Server Files]**.
1. I [!DNL Server Files Manager], klicka **[!UICONTROL Audit]** för att visa innehållet.
1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn bredvid önskad fil och klicka på **[!UICONTROL Make Local]**. En bock visas bredvid filnamnet i dialogrutan [!DNL Temp] kolumn.
1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Granskningsloggen visas i ett nytt fönster i Microsoft Anteckningar.

   ![Steginformation](assets/cfg_accesscontrol_accessFile.png)
