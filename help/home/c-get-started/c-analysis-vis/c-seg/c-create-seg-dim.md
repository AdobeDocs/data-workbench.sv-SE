---
description: Om du vill skapa en segmentdimension börjar du med att göra en markering i en arbetsyta och sedan lägga till segmentet i en visualisering.
solution: Analytics
title: Skapa en segmentdimension
topic: Data workbench
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skapa en segmentdimension{#create-a-segment-dimensions}

Om du vill skapa en segmentdimension börjar du med att göra en markering i en arbetsyta och sedan lägga till segmentet i en visualisering.

**Skapa en segmentdimension**

1. Lägg till en segmentvisualisering på arbetsytan. Exempel:

   ![](assets/vis_Segment.png)

1. Lägg till visualiseringar på arbetsytan som du vill använda för att definiera segmentet och gör sedan de val du vill för att definiera segmentet.
1. I segmentvisualiseringen högerklickar du på etiketten för det segment efter vilket du vill lägga till det nya segmentet och klickar **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Om du vill skapa ett nytt första segment högerklickar du på **[!UICONTROL Segments]** etiketten och klickar på **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   Ett nytt segment (med namnet Nytt segment) visas i visualiseringen. Det andra segmentet representerar alla data som inte ingår i dina definierade segment: är skillnaden mellan era data och era segmentdata.

1. Högerklicka på det nya segmentet och klicka på **[!UICONTROL Rename Segment]**.
1. Skriv ett beskrivande namn för det nya segmentet i namnfältet.

   >[!NOTE]
   >
   >Om ett mätvärde, t.ex. en viss besökare i [!DNL Site], uppfyller villkoren för flera segment, inkluderas mätvärdet endast i det första listade segment som det matchar.

**Spara segmentdimensionen**

1. Högerklicka på segmentetiketten och klicka på **[!UICONTROL Save Dimension]**. Fönstret [!DNL Save Dimension As] visas. Standardplatsen för att spara är användar-\*profilnamnet*\Dimensions-mappen.
1. I [!DNL File name] fältet skriver du ett beskrivande namn för segmenten som du sparar som en dimension och klickar på **[!UICONTROL Save]**.

Du kan komma åt segmentdimensionen när du arbetar med en visualisering. Du kan också exportera data som är kopplade till elementen i den sparade dimensionen med hjälp av segmentexportfunktionen.

Mer information om segmentexportfunktionen och instruktioner om hur du konfigurerar den efter behov finns i [Konfigurera segment för export](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
