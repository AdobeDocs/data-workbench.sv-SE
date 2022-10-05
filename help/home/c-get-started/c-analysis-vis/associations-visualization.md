---
description: Med hjälp av Associationstabellens visualisering kan du koppla mått till mått, dimensioner och dimensionselement med hjälp av Cramers V-algoritm.
title: Visualisering av associationstabell
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# Visualisering av associationstabell{#association-table-visualization}

{{eol}}

Med hjälp av Associationstabellens visualisering kan du koppla mått till mått, dimensioner och dimensionselement med hjälp av Cramers V-algoritm.

I associationstabellen jämförs värden med Cramers V-beräkning i stället för att Pearsons korrelationskoefficient används i [Korrelationsmatris](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html) och [Korrelationskabel](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html) visualiseringar (dessa kan bara jämföra mätvärden, medan associationstabellen och [Associationskanal](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445) kan jämföra mått, dimensioner och element).

## Skapa en associationstabell {#section-87ed12ccc1af4196a1b6534e621c4cbb}

Associationstabellen jämför mått över en räkningsbar eller icke-räkningsbar dimension. Tabellen kan ändras för att framhäva associationer inom visualiseringen genom färgval eller för att återge den som en textruta, värmekarta eller både och.

1. Öppna en associationstabell.

   Högerklicka [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. Välj en utökad dimension - en dimension av typen klickfrekvens, träff, produkt, besök eller besökare. En associationstabell öppnas med den utökade dimensionen som identifieras i hörnet och tillhörande mått placerade i både raden och kolumnen.

   ![](assets/association_table1.png)

   Associationstabellen använder Cramers V som en symmetrisk korrelation, vilket resulterar i valda mått, dimensioner och elementvärden som återspeglas både i kolumnerna och raderna i en associationstabell. Välj till exempel **Produkt** den utökade dimensionen använder **[!UICONTROL Visits]** som det associerade måttet i både raden och kolumnen i tabellen, vilket ger en perfekt men ändå oanvändbar jämförelse (1.00) eftersom de jämförda värdena är identiska.

1. Lägg till fler värden i associationstabellen.

   Högerklicka i en kolumn eller rad och välj **Lägg till mått** eller **Lägg till Dimension**. Du kan också dra mått och mått från en **Finder** -panelen. Dimension-element kan också dras och släppas från en öppen tabell till tabellvisualisering.

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >Det finns en gräns på tio rader och kolumner i associationstabellen.
