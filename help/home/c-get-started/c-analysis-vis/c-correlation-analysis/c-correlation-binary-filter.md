---
description: Med ett binärt filter i korrelationsmatrisen kan du begränsa värden för ett eller båda av de korrelerade måtten för att bättre kunna fokusera jämförelsen.
solution: Analytics
title: Binärt filter i korrelationsmatris
topic: Data workbench
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Binärt filter i korrelationsmatris{#binary-filter-in-the-correlation-matrix}

Med ett binärt filter i korrelationsmatrisen kan du begränsa värden för ett eller båda av de korrelerade måtten för att bättre kunna fokusera jämförelsen.

Så här anger du ett binärt filter för en korrelationsmatris:

1. Högerklicka på ett måttnamn i korrelationsmatrisen.
1. Välj **Redigera måttinformation**.

   ![](assets/correlation_matrix_binary_filter.png)

   Fönstret öppnas **[!UICONTROL Edit Correlation Metric Details]** .

   ![](assets/correlation_matrix_metric_details.png)

1. Konfigurera ett binärt filter.

   Klicka först på **[!UICONTROL Inactive]** inställningen. Den växlar för att ange filtret som **[!UICONTROL Active]** och visar fälten **Jämförelse** och **Värde** .

   Välj sedan en **[!UICONTROL Comparison]** operator och ange dess **[!UICONTROL Value]** för att ställa in ett filter för det valda måttet.

>[!IMPORTANT]
>
>Binärfiltret för Data Workbench 6.2 har uppdaterats med nya funktioner, vilket kräver att du återskapar en korrelationsmatris med ett binärt filter som har skapats i tidigare versioner.

## Lägga till dimensionselement {#section-f19f4e0368ca488e92d1e28bcc24417c}

Du kan också lägga till ett dimensionselement om du vill begränsa ett mått. Ett mätvärde kan bara ha ett associerat element.

![](assets/correlation_matrix_element.png)

Högerklicka på arbetsytan och välj **Tabell**. Öppna en dimension med dess element och dra till **[!UICONTROL Element]** inställningen i fönstret Redigera korrelationsmåttdetaljer eller släpp på ett mått i korrelationsmatrisen.
