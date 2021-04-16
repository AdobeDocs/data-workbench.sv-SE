---
description: Du kan använda kalkylblad för att ange att ett mätvärde har nått ett definierat tröskelvärde.
title: Skapa en måttindikator
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
exl-id: 5713f3dd-85ef-407c-b21c-80e9b4390b6d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# Skapa en måttindikator{#create-a-metric-indicator}

Du kan använda kalkylblad för att ange att ett mätvärde har nått ett definierat tröskelvärde.

Dessutom kan du använda [!DNL Report] för att automatiskt generera och distribuera en rapport när ett mätvärde når ett definierat tröskelvärde inom en angiven tidsram.

Mer information om [!DNL Report] finns i *Data Workbench Report Guide*.

* [Indikator för upp eller ned](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [Kontrollindikator](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**Skapa en måttindikator med hjälp av ett kalkylblad**

1. Definiera innehållet i cellerna i kalkylbladet.

   1. I kolumn A anger du namnet på det önskade måttet (till exempel [!DNL Visitors]).
   1. I kolumn B anger du värdet för det önskade måttet (till exempel [!DNL =Visitors]).
   1. Ange det lägsta tröskelvärdet för måttet i kolumn C.
   1. Ange det övre tröskelvärdet för måttet i kolumn D.
   1. Ange en lämplig formel i kolumn E. Exempel finns i [Uppåtindikatorn eller Nedåtindikatorn](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) eller [Kontrollera indikatorn](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
   1. Högerklicka i formelcellen (kolumn E) och klicka på **[!UICONTROL Format]** > **[!UICONTROL Indicator]** och sedan på något av följande:

      * **[!UICONTROL None]**: Visar den exakta beräkningen i stället för en indikator.
      * **[!UICONTROL Check]**: Använder en bock eller ett X för att ange att värdet antingen är över eller under det tröskelvärde som du anger, beroende på formeln. Se [Kontrollera indikatorn](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
      * **[!UICONTROL Up or Down]**: Använder en upp- eller nedpil för att ange om värdet ligger under det lägsta tröskelvärdet (nedpilen), över det övre tröskelvärdet (uppilen) eller mellan det nedre och det övre tröskelvärdet (tomt). Se [Indikatorn Upp eller Ned](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba).

1. Upprepa steg 1 för andra mätvärden som du vill skapa indikatorer för.

Det resulterande kalkylbladet skulle se ut ungefär som i följande exempel:

![](assets/vis_Worksheet_Alerts.png)

## Indikator för upp eller ned {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

Använd följande formel för [!DNL Up] eller [!DNL Down indicator]:

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

Exempel: [!DNL =(b2-c2)/(d2-c2)*2-1]

Tre utfall är möjliga för varje mätvärde när du använder den här formeln med [!DNL Up] eller [!DNL Down indicator]:

* Om måttvärdet ligger mellan de låga och höga tröskelvärdena beräknas formeln till ett tal mellan -1 och 1 (enbart). Uppåt- eller nedpilen visas inte i kalkylbladet.
* Om måttvärdet är mindre än eller lika med det låga tröskelvärdet utvärderas formeln till ett värde som är mindre än eller lika med -1. Måttindikatorn ändras till en nedpil.
* Om måttvärdet är större än eller lika med det höga tröskelvärdet utvärderas formeln till ett tal som är större än eller lika med 1. Måttindikatorn ändras till en uppåtpil.

Följande kalkylblad visar vad exempelformeln [!DNL =(b2-c2)/(d2-c2)*2-1] skulle visa:

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Kontrollindikator {#section-98c5298a74f34dcbaaf151549fcc7090}

För [!DNL Check indicator] använder du en formel som anger om du vill bli meddelad när måttvärdet är över eller under det tröskelvärde som du anger. Exempel:

* Om du vill få ett meddelande när värdet är under det tröskelvärde du anger kan du använda följande format:

   * [!DNL threshold - metric]

      Exempel: [!DNL =(c2-b2)]

* Om du vill få ett meddelande när värdet ligger över det tröskelvärde du angett kan du använda följande formel:

   * [!DNL metric - threshold]

      Exempel: [!DNL =(b3-c3)]

När en bockmarkering visas utvärderades formeln till ett positivt tal. När ett X visas utvärderades formeln till ett negativt tal.

Det finns två möjliga utfall för varje mätvärde när du använder [!DNL Check indicator]:

* Om formeln anger att det är önskvärt att hålla måttvärdet över tröskelvärdet visas en bock när måttvärdet är större än eller lika med tröskelvärdet och ett X visas när värdet är mindre än tröskelvärdet.
* Om formeln anger att det är önskvärt att hålla måttvärdet under tröskelvärdet visas en bock när måttvärdet är mindre än eller lika med tröskelvärdet och ett X visas när värdet är större än tröskelvärdet.

Följande kalkylblad visar vad exempelformlerna [!DNL =(c2-b2)] och [!DNL =(b3-c3)] skulle visa:

![](assets/vis_Worksheet_Alerts_Check.png)
