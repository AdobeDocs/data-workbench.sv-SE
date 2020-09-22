---
description: Du bör regelbundet övervaka dina händelseloggfiler för att spåra händelsemeddelanden i Insight Server, som loggas till filerna <YYMMDD>-event.txt som finns som standard i händelsemappen i installationskatalogen för Insight Server.
solution: Analytics
title: Övervaka administrativa händelser
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---


# Övervaka administrativa händelser{#monitoring-administrative-events}

Du bör regelbundet övervaka dina händelseloggfiler för att spåra händelsemeddelanden i Insight Server, som loggas till de filer som finns som standard i händelsemappen i installationskatalogen för Insight Server. `<YYYYMMDD>-event.txt`

**Rekommenderad frekvens:** Var 5-10:e minut

Du kan övervaka dessa händelser med hjälp av [!DNL Server Files Manager] i [!DNL Insight], ditt automatiska hanteringsverktyg, [!DNL *-event.txt] filerna eller Windows Event Viewer.

>[!NOTE]
>
>Administrativa händelseloggar är helt skilda från Windows-händelseloggen, men innehåller några av dessa händelser. Loggarna för administrativa händelser innehåller endast information om [!DNL Insight Server] händelser.

**Så här visar du events.txt-filer via[!DNL Server Files Manager]**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för en aktiv bild [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Events]** att visa innehållet.
1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* bredvid önskad fil och klicka på **[!UICONTROL Make Local]**. En bock visas bredvid filnamnet i [!DNL Temp] kolumnen.
1. Högerklicka på bockmarkeringen i [!DNL Temp] kolumnen och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Händelsefilen visas i ett nytt fönster i Microsoft Windows Anteckningar.

   ![Steginformation](assets/vis_FileManager_eventfile.png)

   Filen [!DNL Server.log] i [!DNL Trace] mappen i [!DNL Insight Server] installationskatalogen innehåller mer detaljerad loggningsinformation.

**Så här visar du händelser via Windows Event Viewer**

* Klicka på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Så här ändrar du katalogen Administrativa händelseloggar**

Konfigurationsfilen Administrativa händelseloggar, [!DNL Administrative Events Log.cfg], anger katalogen som händelseloggen ska skickas till.

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.

1. Högerklicka på ikonen för det [!DNL Insight Server] du vill konfigurera och klicka sedan på **[!UICONTROL Server Files]**.

1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL Administrative Event Logs.cfg] katalogen.

1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* för [!DNL Administrative Event Logs.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Administrative Event Logs.cfg].

1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Klicka i [!DNL Administrative Event Logs.cfg] fönstret **[!UICONTROL component]** för att visa innehållet. Standardsökvägen är den [!DNL Events] mapp som finns i [!DNL Insight Server] installationskatalogen.

   ![](assets/cfg_adminevents_examplevalues.png)

1. I parametern Path anger du namnet på den katalog som du vill skicka data för händelseloggning till.
1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.
   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och väljer **[!UICONTROL Save to]** > **[!UICONTROL server name]**.

