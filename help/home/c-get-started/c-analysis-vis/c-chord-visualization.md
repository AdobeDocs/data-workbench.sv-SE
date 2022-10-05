---
description: Med kodvisualiseringen kan du visa både proportionen och korrelationen mellan mätvärden, vilket visar större ord som en indikation på en starkare korrelation.
title: Visualisering av ord
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
exl-id: d712f7b3-de2f-4ca4-a1bf-a2e4d42a084e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# Visualisering av ord{#chord-visualization}

{{eol}}

Med kodvisualiseringen kan du visa både proportionen och korrelationen mellan mätvärden, vilket visar större ord som en indikation på en starkare korrelation.

Med kodvisualiseringen kan du identifiera korrelationer mellan mätvärden, så att du enkelt kan lägga till och utvärdera möjliga korrelationer. Den ger även en annan vy i alla tidigare byggen [Korrelationsmatris](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html). Om du använder kodvisualisering kan du inte identifiera en positiv eller negativ korrelation mellan måtten, utan bara att det finns en korrelation. I vissa fall kan man identifiera en direkt eller omvänd relation genom att använda räknarmått.

1. **Öppna **[!UICONTROL Chord]**visualisering**.

   Högerklicka på arbetsytan [!DNL Visualization > Predictive Analytics > Chord].

1. **Markera en Dimension på menyn**.

   En tom visualisering öppnas där du kan välja en dimension. Dimensionsnamnet visas högst upp i den tomma ordvisualiseringen.

   >[!NOTE]
   >
   >Om du redan har en korrelationsmatris öppen på arbetsytan kan du även återge den som en ordvisualisering.

1. **Välj mätvärden som ska korreleras**.

   Dra mätvärden från **[!UICONTROL Finder]** genom att klicka **[!UICONTROL Ctrl-Alt]** om du vill dra mått från tabellen till diagrammet. När två eller flera mätvärden har valts uppdateras diagrammet automatiskt och du kan börja visa korrelationsdata. Fortsätt lägga till mätvärden efter behov för att korrelera datapunkter.

   ![](assets/chord_drag_metric.png)

   I Nätvisualiseringen visas andelen av hela delen som representeras av området för varje segment. Fortsätt lägga till mätvärden efter behov för att identifiera och undersöka viktiga relationer.

   ![](assets/chord_selected.png)

1. **Visa Chord-visualisering**.

   Håll pekaren över varje mätvärde i visualiseringen för att se hur relationen ser ut. I det här exemplet kan du se en korrelation mellan Enheter och de flesta andra mätvärden (förutom **Besök Varaktighet** mätvärden).

   ![](assets/chord_visualization_1.png)

   När du hovrar över **Besök Varaktighet** mätvärden för Chordvisualisering, ser du att det finns en mycket liten eller svag korrelation mellan alla andra mätvärden.

   ![](assets/chord_visualization_2.png)

1. **Ändra inställningar.** Högerklicka på ordvisualiseringen för att öppna en meny där du kan ändra måttet, visa måtten som absoluta tal eller som procenttal, ta bort det valda måttet eller alla mått, redigera färger och detaljer samt exportera värden till en korrelationsmatris.

   ![](assets/chord_menu.png)
