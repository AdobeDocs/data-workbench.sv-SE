---
description: Med benägenhetsbedömning kan du definiera kunder baserat på deras möjlighet till lyckad konvertering eller slutförande av en viss händelse. Ni kan maximera den potentiella effekten av insatser innan ni kör en process eller leder en kampanj.
title: Propensitetsbedömning
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
exl-id: 832a1e6c-8eeb-4dcc-97e8-9570e1a6eb4f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 0%

---

# Propensitetsbedömning{#propensity-scoring}

{{eol}}

Med benägenhetsbedömning kan du definiera kunder baserat på deras möjlighet till lyckad konvertering eller slutförande av en viss händelse. Ni kan maximera den potentiella effekten av insatser innan ni kör en process eller leder en kampanj.

## Värdet för känslighetsskalförändring {#section-c51ece66effc42de9b754f0f46027c1b}

Med benägenhetsbedömning kan du identifiera dolda beteenden eller mönster som finns i alla dina data. I synnerhet hjälper benägenhetsbedömningen er att identifiera kluster med liknande kunder med mer fokuserade och objektiva metoder i stället för enkel segmentering eller filtrering. Dessutom kan ni med benägenhetsbedömning lägga upp prediktiva funktioner för att identifiera beteende för företagets värdefulla kunder.

När ni har identifierat den värdefulla målgruppen kan ni sedan engagera dem för maximal effekt. Om du till exempel är Business to Business Company kan du ha säljsamtalsleads som gör att du kan poängsätta leads och identifiera deras sannolikhet för att konvertera offline. Eftersom varje lead ökar kostnaderna är det mest effektiva och billigaste sättet att fokusera på era resurser att skapa ett incitament för att identifiera potentiella kunder med störst sannolikhet för att omvandla en försäljning.

Med poängberäkning av sannolikhet kan du identifiera de faktorer som är mest prediktiva för en viss poäng eller öka sannolikheten för att en händelse inträffar, men den kan även användas för att besvara specifika frågor: Kommer kunden att konvertera? Kommer kunden att svara på ett e-postmeddelande? Kommer kunden att köpa tillbaka? Med benägenhetsbedömning kan ni besvara dessa frågor och identifiera besökare med en vilja till åtgärd som sedan kan ställas in och poängsättas.

Dessutom kan du använda filter för att definiera en delmängd av besökare som ska poängsättas med hjälp av det valfria **[!UICONTROL Training Filter]** -funktion. Om inget filter används används alla besökare som mål för poängsättningen.

## Funktioner för Visualisering av benägenhetsbedömning {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Klicka på för att öppna Visualisering av känslighetsbedömning **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

Visualiseringen av poängskalförändring innehåller följande funktioner som är tillgängliga från verktygsfältet:

| Funktionen Verktygsfält | Beskrivning |
|---|---|
| Gå | Klicka för att köra poängprocessen när du har ställt in parametrar. |
| Återställ | Rensa alla inställningar i visualiseringen. |
| Läs in | Läser in en tidigare skapad ScoreDim som gör att du kan ändra och/eller återskapa poängmodellen. |
| Spara | Spara profilbetavisualiseringen som en dim-fil som du kan komma åt och öppna efter behov. |
| Skicka | Skicka betygsuppgift för bearbetning på serversidan. |
| Alternativ | Ange utbildningsfiltret för att begränsa delmängden av besökare. Standardfiltret är **[!UICONTROL Train on Everyone]** men du kan ändra den genom att göra arbetsytemarkeringar eller bygga ett filter med **[!UICONTROL Filter Editor]**. |
| Ange mål | Ange beroende variabel. |
| Mått | Lägg till mått som oberoende variabler. |
| Element | Dra element i Dimensionen med `<Ctrl>` + `<Alt>` tangenter från Dimensioner. |

**Se även**:

* The [Vinst- och lyft-diagram](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). De här vyerna kan öppnas från en komplett bedömningsmodell eller från [!DNL Add Visualization> Predictive Analytics > Scoring.]
* The [Model Viewer](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). De här vyerna kan öppnas från en komplett bedömningsmodell eller från [!DNL Add Visualization> Predictive Analytics > Scoring.]
* The [Komplex filterbeskrivning](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) -funktion.

## Använda visning av benägenhetsbedömning {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Definiera ett eller flera filter för att definiera besökspopulationen för poängsättning**. Detta är valfritt **[!UICONTROL Training Filter]** låter er inrikta er på besökare baserat på valda kriterier. Om inget utbildningsfilter används är alla besökare målinriktade för poängsättning. Om utbildningsfiltret är inställt är poängresultatet meningsfullt för den definierade besökarpopulationen, även om varje besökare fortfarande får ett poängvärde.
* **Identifiera de positiva besökarna**. Definiera den beroende variabeln för att ange ett målfilter som identifierar de positiva besökarna som matchar det önskade resultatet. Det kan vara så enkelt som Intäkter > $10, eller ett mycket mer komplext filter.
* **Målfiltret får inte vara detsamma som utbildningsfiltret**. Logiskt sett bör målfiltret vara ett tillägg till utbildningsfiltret, vilket resulterar i att en positiv delmängd av besökarpopulationen beräknas.
* **Välj variabler av intresse (oberoende variabler) som indata i algoritmen för bedömning av benägenhet**. Dessa kan vara mått eller enskilda element i en Dimension. Propensitetsbedömning startar förbearbetning precis som i [Besökskluster](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). Systemet börjar hämta en viss mängd prov som matchar definitionen av det tidigare angivna utbildningsfiltret (om det finns något). För närvarande anges samplingsstorleken som 10 % av poängpopulationen (definieras av utbildningsfilter), med minst 20 000 och högst 100 000, och är bunden till poängpopulationens storlek.

* En bakgrundsmusik har element från 0 % till 100 % som avgör sannolikheten för att besökarna ska matcha målvariabeln.
