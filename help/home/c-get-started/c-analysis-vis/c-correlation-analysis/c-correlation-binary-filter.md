---
description: Med ett binärt filter i korrelationsmatrisen kan du begränsa värden för ett eller båda av de korrelerade måtten för att bättre kunna fokusera jämförelsen.
title: Binärt filter i korrelationsmatris
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# Binärt filter i korrelationsmatris{#binary-filter-in-the-correlation-matrix}

Med ett binärt filter i korrelationsmatrisen kan du begränsa värden för ett eller båda av de korrelerade måtten för att bättre kunna fokusera jämförelsen.

Så här anger du ett binärt filter för en korrelationsmatris:

1. Högerklicka på ett måttnamn i korrelationsmatrisen.
1. Välj **Redigera måttinformation**.

   ![](assets/correlation_matrix_binary_filter.png)

   Fönstret **[!UICONTROL Edit Correlation Metric Details]** öppnas.

   ![](assets/correlation_matrix_metric_details.png)

1. Konfigurera ett binärt filter.

   Klicka först på inställningen **[!UICONTROL Inactive]**. Den växlar för att ange filtret som **[!UICONTROL Active]** och visar fälten **Jämförelse** och **Värde**.

   Välj sedan en **[!UICONTROL Comparison]**-operator och ställ in dess **[!UICONTROL Value]** för att ställa in ett filter för det valda måttet.

>[!IMPORTANT]
>
>Binärfiltret för Data Workbench 6.2 har uppdaterats med nya funktioner, vilket innebär att du måste återskapa en korrelationsmatris med ett binärt filter som har skapats i tidigare versioner.

## Lägger till Dimension-element {#section-f19f4e0368ca488e92d1e28bcc24417c}

Du kan också lägga till ett dimensionselement om du vill begränsa ett mått. Ett mätvärde kan bara ha ett associerat element.

![](assets/correlation_matrix_element.png)

Högerklicka på arbetsytan och välj **Tabell**. Öppna en dimension med dess element och dra till inställningen **[!UICONTROL Element]** i fönstret Redigera korrelationsmåttdetaljer eller släpp på ett mått i korrelationsmatrisen.
