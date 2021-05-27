---
description: Bildtexter fäster uppmärksamheten på ett visst dimensionselement genom att skapa en ny visualisering med ett virtuellt urval av ett visst dimensionselement i en visualisering.
title: Konfigurera en bildtext
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 0%

---

# Konfigurera en bildtext{#configure-a-callout}

Bildtexter fäster uppmärksamheten på ett visst dimensionselement genom att skapa en ny visualisering med ett virtuellt urval av ett visst dimensionselement i en visualisering.

Du kan lägga till eller redigera bildtexter genom att konfigurera de bildtextfiler som lagras i en profils\*profilnamn*\Context\Callout folder of the [!DNL Server] installationsmapp. Bildtexter som drar uppmärksamheten till ett visst mått i en kalkylbladsvisualisering kallas för metriska bildtexter. Metriska bildtextfiler lagras i profilerna\*profilnamn*\Context\Metric Callout folder.

Instruktioner om hur du lägger till en pratbubbla eller metrisk pratbubbla i en visualisering finns i [Lägga till pratbubblor i en arbetsyta](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Skapa en ny typ av bildtext**

1. I valfri arbetsyta skapar du en visualisering som innehåller de data som du vill ska visas i den nya bildtexttypen. Om du till exempel vill att bildtexten ska vara en tabell skapar du en tabellvisualisering som visar det önskade måttet och måttet.
1. Högerklicka på bildtextfönstrets övre kant och klicka på **[!UICONTROL Save]**.
1. I fönstret [!DNL Save] klickar du på ![](assets/btn_folder_up.png), dubbelklickar på **[!UICONTROL Context]** och dubbelklickar sedan på **[!UICONTROL Callout]**. I fältet [!DNL File Name] anger du ett namn för filen och klickar på **[!UICONTROL Save]**. Bildtextfilen sparas i användarens\*arbetsprofilnamn*\Context\Callout folder.

   >[!NOTE]
   >
   >När du namnger din bildtext väljer du ett beskrivande namn som återspeglar visualiseringstypen och de mått och dimensioner som visas. Om du till exempel vill skapa en bildtext från en tabellvisualisering som visar sessionsmåttet över dagdimensionen, kan du kalla bildtexten&quot;Sessioner efter dagstabell&quot;.

1. (Valfritt) Gör den här ändringen tillgänglig för alla användare av arbetsprofilen:

   1. I [!DNL Profile Manager] klickar du på **[!UICONTROL Context]** och sedan på **[!UICONTROL Callout]**. Den här mappen innehåller alla visualiseringsfiler ( [!DNL .vw]) som definierar de befintliga bildtexttyperna.

   1. Högerklicka på bockmarkeringen bredvid filnamnet för den nya bildtexten i kolumnen [!DNL User] och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Ändra en bildtext till en metrisk bildtext**

1. I [!DNL Profile Manager] klickar du på **[!UICONTROL Context]** och sedan på **[!UICONTROL Callout]**. Den här mappen innehåller alla visualiseringsfiler ( [!DNL .vw]) som definierar de befintliga bildtexttyperna.

1. Högerklicka på bockmarkeringen bredvid filnamnet för den typ av bildtext som du vill ändra och klicka på **[!UICONTROL Make Local]**. När filen har laddats ned till den lokala datorn visas en bock i kolumnen [!DNL User].

1. Högerklicka på bockmarkeringen bredvid filnamnet i kolumnen [!DNL User] och klicka på **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Leta reda på [!DNL metric_y = ref:]-posten i bildtextfilen och ersätt det befintliga värdet med ordet Metrisk. Den markerade texten i följande filfragment visar var du infogar det här ordet.

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

1. Klicka på **[!UICONTROL File]** > **[!UICONTROL Save As]**. I fönstret **[!UICONTROL Save As]** klickar du en gång och dubbelklickar sedan på **[!UICONTROL Metric Callout]**. I fältet [!DNL File Name] anger du ett namn för filen och klickar på **[!UICONTROL Save]**. Bildtextfilen för måttet sparas i användarens\*arbetsprofilnamn*\Context\Metric Callout folder.

1. (Valfritt) Om du vill göra den här metriska bildtexten tillgänglig för alla användare i arbetsprofilen högerklickar du i [!DNL Profile Manager] på bockmarkeringen bredvid filnamnet i kolumnen [!DNL User] och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
