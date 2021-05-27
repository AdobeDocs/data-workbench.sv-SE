---
description: Du bör regelbundet övervaka dina händelseloggfiler för att spåra händelsemeddelanden i Insight Server, som loggas till filerna <YYMMDD>-event.txt som finns som standard i händelsemappen i installationskatalogen för Insight Server.
title: Övervaka administrativa händelser
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---

# Övervaka administrativa händelser{#monitoring-administrative-events}

Du bör regelbundet övervaka dina händelseloggfiler för att spåra systemhändelsemeddelanden för Insight Server, som loggas till `<YYYYMMDD>-event.txt`-filer som finns som standard i händelsemappen i installationskatalogen för Insight Server.

**Rekommenderad frekvens:** var 5-10:e minut

Du kan övervaka dessa händelser med [!DNL Server Files Manager] i [!DNL Insight], ditt automatiska hanteringsverktyg, [!DNL *-event.txt]-filerna eller Windows Event Viewer.

>[!NOTE]
>
>Administrativa händelseloggar är helt skilda från Windows-händelseloggen, men innehåller några av dessa händelser. Loggarna för administrativa händelser innehåller bara information om [!DNL Insight Server]-händelser.

**Så här visar du events.txt-filer via[!DNL Server Files Manager]**

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för en aktiv [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.
1. Klicka på **[!UICONTROL Events]** i [!DNL Server Files Manager] för att visa innehållet.
1. Högerklicka på bockmarkeringen i kolumnen *servernamn* bredvid önskad fil och klicka på **[!UICONTROL Make Local]**. En bock visas bredvid filnamnet i kolumnen [!DNL Temp].
1. Högerklicka på bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Händelsefilen visas i ett nytt fönster i Microsoft Windows Anteckningar.

   ![Steginformation](assets/vis_FileManager_eventfile.png)

   Filen [!DNL Server.log] i mappen [!DNL Trace] i installationskatalogen [!DNL Insight Server] innehåller mer detaljerad loggningsinformation.

**Så här visar du händelser via Windows Event Viewer**

* Klicka på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**Så här ändrar du katalogen Administrativa händelseloggar**

Konfigurationsfilen [!DNL Administrative Events Log.cfg] för den administrativa händelseloggen anger katalogen som händelseloggen ska skickas till.

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för [!DNL Insight Server] som du vill konfigurera och klicka på **[!UICONTROL Server Files]**.

1. Klicka på **[!UICONTROL Components]** i [!DNL Server Files Manager] för att visa innehållet. Filen [!DNL Administrative Event Logs.cfg] finns i den här katalogen.

1. Högerklicka på bockmarkeringen i kolumnen *servernamn* för [!DNL Administrative Event Logs.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i kolumnen [!DNL Temp] för [!DNL Administrative Event Logs.cfg].

1. Högerklicka på den nya bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. I fönstret [!DNL Administrative Event Logs.cfg] klickar du på **[!UICONTROL component]** för att visa innehållet. Standardsökvägen är mappen [!DNL Events] i installationskatalogen för [!DNL Insight Server].

   ![](assets/cfg_adminevents_examplevalues.png)

1. I parametern Path anger du namnet på den katalog som du vill skicka data för händelseloggning till.
1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.
   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och väljer **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
