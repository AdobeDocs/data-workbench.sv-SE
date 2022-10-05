---
description: Om du vill skapa en segmentdimension börjar du med att göra en markering i en arbetsyta och sedan lägga till segmentet i en visualisering.
title: Skapa en segmentdimension
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Skapa en segmentdimension{#create-a-segment-dimensions}

{{eol}}

Om du vill skapa en segmentdimension börjar du med att göra en markering i en arbetsyta och sedan lägga till segmentet i en visualisering.

**Skapa en segmentdimension**

1. Lägg till en segmentvisualisering på arbetsytan. Exempel:

   ![](assets/vis_Segment.png)

1. Lägg till visualiseringar på arbetsytan som du vill använda för att definiera segmentet och gör sedan de val du vill för att definiera segmentet.
1. Högerklicka på etiketten för det segment efter vilket du vill lägga till det nya segmentet i segmentvisualiseringen och klicka sedan på **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Om du vill skapa ett nytt första segment högerklickar du på **[!UICONTROL Segments]** etikett och klicka **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   Ett nytt segment (med namnet Nytt segment) visas i visualiseringen. Det andra segmentet representerar alla data som inte ingår i dina definierade segment: är skillnaden mellan era data och era segmentdata.

1. Högerklicka på det nya segmentet och klicka på **[!UICONTROL Rename Segment]**.
1. Skriv ett beskrivande namn för det nya segmentet i namnfältet.

   >[!NOTE]
   >
   >Om ett måttvärde, till exempel en viss besökare i [!DNL Site], uppfyller villkoren för flera segment, inkluderas måttvärdet endast i det första listade segmentet som det matchar.

**Spara segmentdimensionen**

1. Högerklicka på segmentetiketten och klicka på **[!UICONTROL Save Dimension]**. The [!DNL Save Dimension As] visas. Standardplatsen för att spara är mappen User\*profile name*\Dimensions.
1. I [!DNL File name] anger du ett beskrivande namn för de segment som du sparar som en dimension och klickar på **[!UICONTROL Save]**.

Du kan komma åt segmentdimensionen när du arbetar med en visualisering. Du kan också exportera data som är kopplade till elementen i den sparade dimensionen med hjälp av segmentexportfunktionen.

Mer information om segmentexportfunktionen och instruktioner om hur du konfigurerar det efter behov finns i [Konfigurera segment för export](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
