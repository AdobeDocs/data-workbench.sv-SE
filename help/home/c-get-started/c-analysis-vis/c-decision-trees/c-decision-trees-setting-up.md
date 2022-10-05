---
description: Skapa ett beslutsträd genom att identifiera ett positivt fall och lägga till mått och dimensioner för att utvärdera data och utforska beslutsträdet.
title: Bygga ett beslutsträd
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
exl-id: 06db9e77-72ea-44c7-8451-d3f195acd196
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---

# Bygga ett beslutsträd{#building-a-decision-tree}

{{eol}}

Skapa ett beslutsträd genom att identifiera ett positivt fall och lägga till mått och dimensioner för att utvärdera data och utforska beslutsträdet.

Följ de här stegen för att skapa ett beslutsträd.

1. Öppna en ny arbetsyta.

   När du har öppnat en ny arbetsyta kan du behöva klicka **Lägg till** > **Lås upp tillfälligt**.

1. Högerklicka för att öppna beslutsträdsbyggaren **[!UICONTROL Visualization]** > **Prediktiv analys** > **Klassificering** > **Beslutsträdsbyggaren**.

1. Ange en **Positivt skiftläge**.

   Du kan definiera ett positivt skiftläge för ett beslutsträd genom att välja dimensioner i en Finder- eller dimensionselement i en tabell, eller genom att utforma ett filter i designfiltret. Det positiva fallet kan vara en kombination av flera markeringar på arbetsytan, inklusive filter, dimensioner, element och alla typer av visualiseringsvärden för Data Workbench.

   * **Utforma och tillämpa ett filter** som ett positivt fall. Högerklicka på arbetsytan och välj **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** för att utforma och använda ett filter.

   * Lägg till **Dimensioner** som ett positivt fall. Högerklicka på arbetsytan och välj **verktyg** > **Finders** (eller markera **[!UICONTROL Add]** > **[!UICONTROL Finders]** i den vänstra rutan). Ange ett dimensionsnamn i **Sök** och välj sedan en dimension.

   * Lägg till **Mått** som ett positivt fall. Högerklicka och välj **verktyg** > **Finders** eller markera **[!UICONTROL Add]** > **[!UICONTROL Finders]** i den vänstra rutan för att öppna en Metrics-tabell. Välj ett mått som positivt skiftläge.

   * Lägg till **Dimension Elements** som ett positivt fall. Högerklicka på arbetsytan och välj **[!UICONTROL Table]** för att öppna dimensionselement väljer du sedan ett av dimensionselementen för att ställa in ditt positiva skiftläge.

1. Klicka på **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   Detta anger det positiva skiftläget och låter dig namnge det. Namnet visas under **[!UICONTROL Positive Case]** i arbetsytan.

   >[!NOTE]
   >
   >När du anger ett positivt fall använder beslutsträdet den aktuella arbetsytemarkeringen, som kan definieras som besökare (eller någon annan räkningsbar översta nivå har definierats, men i de flesta fall besökare) som matchar den aktuella markeringen på arbetsytan. Dessa kombineras som ett enda filter för ett enda positivt fall (inte flera positiva fall).

   Klicka **[!UICONTROL Set Positive Case]** när det inte finns någon markering raderas det positiva fallet.

1. (valfritt) Välj **[!UICONTROL Set Population Filters]** för att definiera besökspopulationen som ska klassificeras.

   Om inget populationsfilter används, ritas träningsuppsättningen från alla besökare (standard är &quot;Alla&quot;).

   >[!NOTE]
   >
   >Klicka på **[!UICONTROL Show Complex Filter Description]** om du vill visa filtreringsskript för filtret Positivt skiftläge och Population.

1. Lägg till **Mått**, **Dimensioner** och **Dimension Elements** som indata.

   Du kan välja indata genom att dra och släppa från Finder-panelerna eller från tabeller för enskilda dimensionselement. Du kan också välja i **[!UICONTROL Metrics]** i verktygsfältet.

   * Lägg till **Mått** som indata.

      Välj Metrisk i verktygsfältet. Tryck **Ctrl** + **Alt** om du vill dra en eller flera mätvärden till beslutsträdsbyggaren.

      Måtten visas i **Lista över indata (mått)** som indata med unik färgkodning.

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * Lägg till **Dimensioner** som indata.

      Högerklicka på arbetsytan och välj **verktyg** > **Finder** och skriv dimensionsnamnet i **Sök** fält. Tryck **Ctrl** + **Alt**, välj en dimension och dra dimensionen till beslutsträdsbyggaren.

      Dimensionen visas i **Indata (Dimensioner)** lista med unik färgkodning.

   * Lägg till **Dimension Elements** som indata.

      Högerklicka på arbetsytan och markera en Dimension. Markera Dimension Elements, tryck på **Ctrl** + **Alt** och dra de markerade elementen till beslutsträdsbyggaren.

      Dimensionselementen visas i **Indata (element)** lista med unik färgkodning.
   >[!IMPORTANT]
   >
   >Du kan välja upp till 14 indata som ska utvärderas. Ett felmeddelande visas om för många indata läggs till.

1. Välj **[!UICONTROL Go]** i verktygsfältet.

   Beslutsträdet kommer att bygga baserat på valda dimensioner och mätvärden. Enkla mätvärden som t.ex. kundvagnstillägg kommer att byggas snabbt, medan komplexa dimensioner som Visit Duration med flera datapunkter kommer att byggas långsammare med en procentandel av färdigställandet som visas när det konverteras. Trädkartan kommer sedan att rensas och öppnas för användarinteraktion. Dimensions- och mätvärdena färgkodas enligt nodnamnen.

   ![](assets/decision_tree_builder.png)

   Lövnoden visas som grön (true) eller röd (false) om trädet har rensats och om det finns en prognos för **True** eller **Falskt** efter de rensade grenarna.

   >[!NOTE]
   >
   >Utbildningsexemplet hämtas från datauppsättningen så att trädbyggaren kan använda det. Datan Workbench använder 80 % av samplingen för att bygga trädet och de återstående 20 procenten för att utvärdera trädmodellens exakthet.

1. Verifiera exaktheten med **[!UICONTROL Confusion Matrix]**.

   Klicka **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** för att visa värdena Accuracy, Recall, Precision och F-Score. Ju närmare 100 procent, desto bättre blir poängen.

   Med konfusionsmatrisen får du fyra noggrannhetsvärden för modellen med en kombination av värden:

   * Faktiskt positivt (AP)
   * Förutsedd positiv (PP)
   * Verkligt negativ (AN)
   * Förutsedd negativ (PN)

   >[!TIP]
   >
   >Dessa siffror erhålls genom att använda den resulterande poängmodellen för de 20-procentiga testdata som behålls och som redan kallas det sanna svaret. Om poängen är större än 50 procent förutspås det som ett positivt skiftläge (som matchar det definierade filtret). Sedan, Accuracy = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) och Precision = TP / (TP + FP).

1. **Utforska beslutsträdet**.

   När du har skapat ett beslutsträd kan du visa sökvägen för förutsägelsen och identifiera alla besökare som uppfyller de definierade kriterierna. Trädet identifierar indatadelningen för varje gren baserat på dess position och färgkodning. Om du t.ex. markerar noden Refererande domän, visas de noder som leder till den delningen som färgkod till vänster om trädet.

   Du kan göra val av lövnoderna för att välja grenar (regeluppsättningar) av beslutsträdet.

   I det här exemplet: Om besökets längd är mindre än 1 finns det ingen kampanj, det finns minst en sidvy, det finns inga e-postregistreringar och det fanns minst ett besök. Prognoserna för detta möteskriterier och beställningens placering är **94,73** procent.

   ![](assets/decision_tree_explore.png)

   **Interaktion med beslutsträd**: Du kan välja flera noder i trädet med hjälp av standardinställningarna **Ctrl-klicka** att lägga till, eller **Skift-klicka** att ta bort.

   **Färgkodade noder**: Färgen på noderna matchar färgen på indatamåtten och mätvärdena som tilldelats av Datan Workbench.

   Ljusgröna och röda noder på lövnivå i en rensad gren förutsäger att noden är True eller False.

   | ![](assets/decision_tree_node_true.png) Ljusgrön | Identifierar att noden är lika med true och att alla villkor är uppfyllda. |
   |---|---|
   | ![](assets/decision_tree_node_false.png) Ljusröd | Identifierar att noden är lika med false och att inte alla villkor är uppfyllda. |

1. **Spara beslutsträdet**.

   Du kan spara beslutsträdet i olika format:

   ![](assets/decison_tree_save.png)

   * Predictive Markup Language (**PMML**), ett XML-baserat filformat som används av program för att beskriva och utbyta beslutsträdsmodeller.
   * **Text** visa enkla kolumner och rader med true eller false, procentandelar, antal medlemmar och indatavärden.
   * A **Dimension** med förgreningar som motsvarar förväntade resultatelement.
