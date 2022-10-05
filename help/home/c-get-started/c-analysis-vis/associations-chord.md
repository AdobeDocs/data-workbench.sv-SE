---
description: Med Association Chord-visualisering kan du visa både proportionen och associationen mellan mått, dimensioner och element och visa större ord som en indikation på en starkare association.
title: Visualisering av associationskord
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
exl-id: e71394ef-4895-4a3e-912d-d6f56ca8f001
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---

# Visualisering av associationskord{#association-chord-visualization}

{{eol}}

Med Association Chord-visualisering kan du visa både proportionen och associationen mellan mått, dimensioner och element och visa större ord som en indikation på en starkare association.

Associations Table jämför värden med Cramer&#39;s V-beräkning i stället för att använda Pearsons korrelationskoefficient som används i [Korrelationsmatris](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) och [Korrelationskabel](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) visualiseringar (dessa kan bara jämföra mätvärden, medan Association Table och Chord kan jämföra mått, dimensioner och element). Associeringskedjan ger även en annan vy i en tidigare byggd [Associationstabell](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f).

**Så här skapar du en associationskabel**

1. Högerklicka på en arbetsyta **Visualisering > Predictive Analytics > Association Chord**.

   En meny öppnas där du kan välja en utökad dimension från listan.

   ![](assets/association_chord1.png)

   När du har valt det här alternativet öppnas den tomma associationstabellen med den markerade Dimensionen i titeln. ![](assets/association_chord2.png)

1. **Välj ett mått-, dimension- eller dimensionselement**.

   Högerklicka på ordvisualiseringen och välj **Lägg till mått** eller **Lägg till Dimension**. Välj de alternativ på menyn som du vill lägga till i ordet.

   Du kan också dra mått och mått från **[!UICONTROL Finder]** genom att klicka **[!UICONTROL Ctrl-Alt]** och dra mätvärden och mått till ackordet. Du kan också dra dimensionselement direkt från en öppen tabell till kodvisualiseringen.

1. **Välj ytterligare mått, dimensioner och element att associera**.

   När två eller flera värden har valts uppdateras diagrammet automatiskt och associationsdata visas. Fortsätt lägga till mätvärden efter behov för att koppla datapunkter.

   ![](assets/association_chord.png)

   I Nätvisualiseringen visas andelen av hela delen som representeras av området för varje segment. Fortsätt lägga till mått/dimensioner/element efter behov för att identifiera och undersöka viktiga relationer.

1. **Visa Chord-visualisering**.

   Håll pekaren över varje värde i visualiseringen för att se relationerna.

1. **Ändra inställningar.** Högerklicka på ordvisualiseringen för att öppna en meny och ändra måtten, måtten eller elementen så att måtten visas som absoluta tal eller som procenttal, ta bort det valda måttet eller alla mått, redigera färger och detaljer samt exportera värden till en associationstabell.

**Så här skapar du en associationskabel från en associationstabell:**

1. Öppna en **Associationstabell** visualisering.
1. Högerklicka och välj **Exportera ordvisualisering**. Ett koppelordsdiagram öppnas med värden markerade i associationstabellen. ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>Om du exporterar en associationstabell från ett associationskorddiagram som innehåller minst ett mått, dupliceras elementen i rader/kolumner i associationstabellen. Om du vill undvika duplicerade element skapar du en ny associationstabell och lägger till de önskade elementen i stället för att exportera elementen från ett associationskorddiagram.
