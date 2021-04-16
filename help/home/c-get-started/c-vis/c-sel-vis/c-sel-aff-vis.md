---
description: I en arbetsyta representerar en visualisering en uppsättning frågeresultat.
title: Förstå hur en markering påverkar andra visualiseringar
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Förstå hur en markering påverkar andra visualiseringar{#understanding-how-a-selection-affects-other-visualizations}

I en arbetsyta representerar en visualisering en uppsättning frågeresultat.

När du gör en markering filtrerar Data Workbench resultatet av de frågor som används för att skapa visualiseringar på arbetsytan. Det specifika filtret varierar beroende på visualisering.

Följande exempel visar hur Data Workbench använder en markering på tre olika typer av visualiseringar. Om du tittar på de här exemplen får du hjälp med att förstå vilken filtereffekt som markeringar har på visualiseringar. De hjälper dig även att förstå hur du tolkar de resultat du ser i en filtrerad visualisering.

* [Filtrera en visualisering med ett sessionsmått](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Filtrera en visualisering med en besökarmätning](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Filtrera en visualisering med ett besöks-för-session-mått](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Filtrera en visualisering med ett sessionsmått {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

I det här exemplet filtrerar URI:n [!DNL /direct.asp/?ldPage=hme] i visualiseringen till vänster måtten för sessioner som visas i visualiseringen till höger.

![](assets/client-vis1.png)

* **Markeringens effekt på frågan:** Datan Workbench filtrerar sessionerna för den valda URI:n. I det här exemplet filtreras frågan som genererar värdet för [!DNL /pops/disclosure_pop.asp]-elementet på följande sätt:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **Tolka visualiseringen:** Den filtrerade visualiseringen representerar antalet sessioner som innehåller de URI:er som anges i visualiseringen och  [!DNL /direct.asp/?ldPage=hme]. I det här exemplet visas att det fanns 1 113 sessioner där besökarna visade både [!DNL /pops/disclosure_pop.asp]-sidan och [!DNL /direct.asp/?ldPage=hme] i samma session.

## Filtrera en visualisering med ett besökarmått {#section-97d38c7f03e8457189a9c72d69514ed2}

I det här exemplet filtrerar URI:n [!DNL /direct.asp/?ldPage=home] i visualiseringen till vänster måttet för besökare i visualiseringen till höger.

![](assets/client-vis2.png)

* **Markeringens effekt på frågan:** Datan Workbench filtrerar besökarna för den valda URI:n. I det här exemplet filtreras frågan som genererar värdet för URI:n [!DNL /pops/disclosure_pop.asp] enligt följande:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **Tolka visualiseringen:** Den filtrerade visualiseringen avbildar de besökare som har visat de URI:er som anges i visualiseringen  [!DNL /direct.asp/?ldPage=hme] (även om det inte nödvändigtvis sker under samma session). Exemplet ovan visar att 2 041 besökare har visat både [!DNL /pops/disclosure_pop.asp] och [!DNL /direct.asp/?ldPage=hme].

## Filtrera en visualisering med ett besökare-för-session-mått {#section-f746182311d648dcb98716b0fe846e25}

I det här exemplet filtrerar URI:n [!DNL /direct.asp/?ldPage=hme] i visualiseringen till vänster måttet för besökare-för-session i visualiseringen till höger.

![](assets/client-vis3.png)

* **Markeringens effekt på frågan:** Datan Workbench filtrerar besökarna efter session för den valda URI:n. Frågan som genererar värdet för URI:n [!DNL /pops/disclosure_pop.asp] filtreras till exempel enligt följande:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **Tolka visualiseringen:** Den filtrerade visualiseringen avbildar de besökare som har visat båda URI:erna som listas i visualiseringen och  [!DNL /direct.asp/?ldPage=hme] under samma session. I det här exemplet visas att 1 069 besökare både såg [!DNL /pops/disclosure_pop.asp] och [!DNL /direct.asp/?ldPage=hme] under en session.
