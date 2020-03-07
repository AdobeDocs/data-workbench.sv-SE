---
description: Bildtexter fäster uppmärksamheten på ett visst dimensionselement genom att skapa en ny visualisering med ett virtuellt urval av ett visst dimensionselement i en visualisering.
solution: Analytics
title: Konfigurera en bildtext
topic: Data workbench
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera en bildtext{#configure-a-callout}

Bildtexter fäster uppmärksamheten på ett visst dimensionselement genom att skapa en ny visualisering med ett virtuellt urval av ett visst dimensionselement i en visualisering.

Du kan lägga till eller redigera bildtexter genom att konfigurera de bildtextfiler som lagras i en profil\*profilnamn*\Context\Callout folder of the [!DNL Server] installationsmapp. Bildtexter som drar uppmärksamheten till ett visst mått i en kalkylbladsvisualisering kallas för metriska bildtexter. Metriska bildtextfiler lagras i profilerna\*profilnamn*\Context\Metric Callout folder.

Instruktioner om hur du lägger till en pratbubbla eller metrisk pratbubbla i en visualisering finns i [Lägga till pratbubblor på en arbetsyta](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Skapa en ny typ av bildtext**

1. I valfri arbetsyta skapar du en visualisering som innehåller de data som du vill ska visas i den nya bildtexttypen. Om du till exempel vill att bildtexten ska vara en tabell skapar du en tabellvisualisering som visar det önskade måttet och måttet.
1. Högerklicka på bildtextfönstrets övre kant och klicka **[!UICONTROL Save]**.
1. Klicka i [!DNL Save] fönstret ![](assets/btn_folder_up.png), dubbelklicka **[!UICONTROL Context]** och dubbelklicka sedan **[!UICONTROL Callout]**. Skriv ett namn på filen i [!DNL File Name] fältet och klicka på **[!UICONTROL Save]**. Bildtextfilen sparas i användarens\*arbetsprofilnamn*\Context\Callout folder.

   >[!NOTE]
   >
   >När du namnger din bildtext väljer du ett beskrivande namn som återspeglar visualiseringstypen och de mått och dimensioner som visas. Om du till exempel vill skapa en bildtext från en tabellvisualisering som visar sessionsmåttet över dagdimensionen, kan du kalla bildtexten&quot;Sessioner efter dagstabell&quot;.

1. (Valfritt) Gör den här ändringen tillgänglig för alla användare av arbetsprofilen:

   1. Klicka i [!DNL Profile Manager]och **[!UICONTROL Context]** sedan på **[!UICONTROL Callout]**. Den här mappen innehåller alla visualiseringsfiler ( [!DNL .vw]) som definierar de befintliga bildtexttyperna.

   1. Högerklicka på bockmarkeringen bredvid filnamnet för den nya bildtexten i [!DNL User] kolumnen och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Ändra en bildtext till en metrisk bildtext**

1. Klicka i [!DNL Profile Manager]och **[!UICONTROL Context]** sedan på **[!UICONTROL Callout]**. Den här mappen innehåller alla visualiseringsfiler ( [!DNL .vw]) som definierar de befintliga bildtexttyperna.

1. Högerklicka på bockmarkeringen bredvid filnamnet för den typ av bildtext som du vill ändra och klicka sedan på **[!UICONTROL Make Local]**. När filen har laddats ned till den lokala datorn visas en bock i [!DNL User] kolumnen.

1. Högerklicka på bockmarkeringen bredvid filnamnet i [!DNL User] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Leta reda på [!DNL metric_y = ref:] posten i bildtextfilen och ersätt det befintliga värdet med ordet Metrisk. Den markerade texten i följande filfragment visar var du infogar det här ordet.

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

1. Klicka på **[!UICONTROL File]** > **[!UICONTROL Save As]**. Klicka en gång i **[!UICONTROL Save As]** fönstret och dubbelklicka sedan **[!UICONTROL Metric Callout]**. Skriv ett namn på filen i [!DNL File Name] fältet och klicka på **[!UICONTROL Save]**. Bildtextfilen för måttet sparas i användarens\*arbetsprofilnamn*\Context\Metric Callout folder.

1. (Valfritt) Om du vill att den här metriska bildtexten ska vara tillgänglig för alla som använder arbetsprofilen, högerklickar du i [!DNL Profile Manager]kryssrutan bredvid filnamnet i [!DNL User] kolumnen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

