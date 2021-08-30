---
description: Med trendlinjer kan du täcka över diagram för att jämföra och tolka data.
title: Trendlinjer
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
exl-id: 3e7e9218-49b2-4877-a4bd-318b838089e8
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Trendlinjer{#trend-lines}

Med trendlinjer kan du täcka över diagram för att jämföra och tolka data.

Precis som visualiseringen [Spridningspunkt](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-scat-plots.html) kan du nu ange trendlinjer i en grafvisualisering för att visa ändringshastigheten baserat på linjer som är linjära, exponentiella, kraftfulla eller polynominella. Med funktionen Trend Line kan du täcka över trendlinjer i ett diagram, vanligtvis över en tidsdimension.

I den här diagramjämförelsen ser vi till exempel att besöken trunkeras, men att beställningarna trunkeras.

![](assets/trend_line.png)

Lägga till en trendlinje

1. Öppna ett diagram och högerklicka på måttnamnet i det övre vänstra hörnet.
1. Klicka på **[!UICONTROL Trend Lines]** och välj bland alternativen.

   ![](assets/trend_line_graph.png)

   Du kan markera den trendlinje som ska visas över diagrammet som **Enkel linjär**, **Exponentiell**, **Power** eller **Polynomial**. Polynomial kommer att skapa en trendlinje för polynominell regression. Enkelt Linjärt skapar en trendlinje som förändringshastigheten längs regressionslinjen. Exponentiell beräknar en trendlinje som y = b*exp( a*x ) och potens som y = b*x`<sup>a</sup>`.

   Trenden beräknas och återges i diagrammet, och en bildtext med detaljerad information om trendekvationen öppnas.

   ![](assets/trend_line_detail.png)
