---
description: Bildtexter fäster uppmärksamheten på ett visst dimensionselement genom att skapa en ny visualisering med ett virtuellt urval av ett visst dimensionselement i en visualisering.
title: Konfigurera en bildtext
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 0%

---

# Konfigurera en bildtext{#configure-a-callout}

{{eol}}

Bildtexter fäster uppmärksamheten på ett visst dimensionselement genom att skapa en ny visualisering med ett virtuellt urval av ett visst dimensionselement i en visualisering.

Du kan lägga till eller redigera bildtexter genom att konfigurera bildtextfiler som lagras i profilerna\*profilnamn*\Kontext\Bildtextmappen i [!DNL Server] installationsmapp. Bildtexter som drar uppmärksamheten till ett visst mått i en kalkylbladsvisualisering kallas för metriska bildtexter. Metriska bildtextfiler lagras i profilerna\*profilnamn*\Context\Metric Callout-mappen.

Instruktioner om hur du lägger till en pratbubbla eller metrisk pratbubbla i en visualisering finns i [Lägga till bildtexter på en arbetsyta](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Skapa en ny typ av bildtext**

1. I valfri arbetsyta skapar du en visualisering som innehåller de data som du vill ska visas i den nya bildtexttypen. Om du till exempel vill att bildtexten ska vara en tabell skapar du en tabellvisualisering som visar det önskade måttet och måttet.
1. Högerklicka på bildtextfönstrets övre kant och klicka på **[!UICONTROL Save]**.
1. I [!DNL Save] fönster, klicka ![](assets/btn_folder_up.png), dubbelklicka **[!UICONTROL Context]** dubbelklicka **[!UICONTROL Callout]**. I [!DNL File Name] anger du ett namn för filen och klickar på **[!UICONTROL Save]**. Bildtextfilen sparas i användar-\*arbetsprofilens namn*\Kontext\Bildtextmappen.

   >[!NOTE]
   >
   >När du namnger din bildtext väljer du ett beskrivande namn som återspeglar visualiseringstypen och de mått och dimensioner som visas. Om du till exempel vill skapa en bildtext från en tabellvisualisering som visar sessionsmåttet över dagdimensionen, kan du kalla bildtexten&quot;Sessioner efter dagstabell&quot;.

1. (Valfritt) Gör den här ändringen tillgänglig för alla användare av arbetsprofilen:

   1. I [!DNL Profile Manager], klicka **[!UICONTROL Context]** och sedan klicka **[!UICONTROL Callout]**. Den här mappen innehåller alla visualiseringsfiler ( [!DNL .vw]) som definierar de befintliga bildtexttyperna.

   1. Högerklicka på bockmarkeringen bredvid filnamnet för den nya bildtexten i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Ändra en bildtext till en metrisk bildtext**

1. I [!DNL Profile Manager], klicka **[!UICONTROL Context]** och sedan klicka **[!UICONTROL Callout]**. Den här mappen innehåller alla visualiseringsfiler ( [!DNL .vw]) som definierar de befintliga bildtexttyperna.

1. Högerklicka på bockmarkeringen bredvid filnamnet för den typ av bildtext som du vill ändra och klicka på **[!UICONTROL Make Local]**. När filen har laddats ned till den lokala datorn visas en bock i [!DNL User] kolumn.

1. Högerklicka på bockmarkeringen bredvid filnamnet i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Leta reda på [!DNL metric_y = ref:] i bildtextfilen och ersätt det befintliga värdet med ordet Metrisk. Den markerade texten i följande filfragment visar var du infogar det här ordet.

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. Klicka på **[!UICONTROL File]** > **[!UICONTROL Save As]**. I **[!UICONTROL Save As]** fönster, klicka en gång och dubbelklicka sedan **[!UICONTROL Metric Callout]**. I [!DNL File Name] anger du ett namn för filen och klickar på **[!UICONTROL Save]**. Den måttbaserade bildtextfilen sparas i användar-\*arbetsprofilens namn*\Context\Metric Callout-mappen.

1. (Valfritt) Om du vill att den här metriska pratbubblan ska vara tillgänglig för alla användare i arbetsprofilen går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen bredvid filnamnet i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
