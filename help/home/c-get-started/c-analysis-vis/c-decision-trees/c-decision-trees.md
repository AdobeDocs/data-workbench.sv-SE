---
description: Beslutsträd är en visualisering för prediktiv analys som används för att utvärdera besökares egenskaper och relationer. Beslutsträdsbyggaren genererar en beslutsträdsvisualisering baserad på ett angivet positivt fall och en uppsättning indata.
solution: Analytics
title: Beslutsträdsbyggaren
topic: Data workbench
uuid: 1f7e91ea-e5d9-4d8e-9fcf-cae4de42dfdd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Beslutsträdsbyggaren{#decision-tree-builder}

Beslutsträd är en visualisering för prediktiv analys som används för att utvärdera besökares egenskaper och relationer. Beslutsträdsbyggaren genererar en beslutsträdsvisualisering baserad på ett angivet positivt fall och en uppsättning indata.

Ett beslutsträd är en binär klassificerare med en uppsättning regler (eller filter) som identifierar besökare som uppfyller specifika regler baserade på ett positivt fall. Ett beslutsträd anger regler för att klassificera besökare som uppfyller (eller inte uppfyller) detta positiva fall. Dessa regler genererar en trädkarta som ger en viss grad av förtroende för att uppnå dessa positiva ärenderesultat.

Ett beslutsträd byggs genom att man undersöker indata på varje nivå och väljer det som ger maximal informationsvinst vid en viss delningspunkt. Delningspunkter för varje variabelnivå genererar två uppsättningar:

* värden som är mindre än eller lika med delningspunkten, och
* Värden större än delningspunkten.

Använd beslutsträd för att

* Genomför meningsfulla analyser och tolkningar på kortare tid.
* Använd automatiserad segmentgenerering.
* Skapa snabbt slutsatser utifrån en modell som bygger på en stor mängd data.

![](assets/decision_tree_parts.png)

<table id="table_FCC5D63EF8A843D79B2338BD951025EA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Verktygsfält och menyer</b> </p> <p>Verktygsfältet innehåller knappar och menykommandon för beslutsträdet, inklusive funktioner för att ställa in positiv skiftläge och lägga till inmatningslistor. </p> <p>Precis som med andra visualiseringar kan du dra och släppa dimensioner och element i rutan <span class="uicontrol"> Element</span> , men du kan även dra direkt från rutan Finders. </p> <p>Mer information finns i Alternativ <a href="../../../../home/c-get-started/c-analysis-vis/c-decision-trees/c-decision-trees-menu.md#concept-bfc4e80651a243d3966cc770b205606c"> för beslutsträd</a>. </p> </td> 
   <td colname="col2"> <p><b>Inmatningslista</b> </p> <p>I det här området visas indata i trädmodellen. De är färgkodade så att de matchar noderna i trädvisningsområdet. </p> <p>Om du högerklickar på en inmatning kan du ta bort inmatningen från modellen och återställa den. </p> <p>Om du hovrar över en trädnod visas delningsvillkoren längs grenen till den noden och förutsägelsen vid den noden med dess konfidensvärde. </p> </td> 
   <td colname="col3"> <p><b>Trädvisning</b> </p> <p>I det här området visas trädmodellen med lövnoder som är färgkodade baserat på dess förutsägelse: grönt för en True-förutsägelse av det positiva fallet och rött för en False-förutsägelse. </p> <p>De delade noderna färgkodas enligt de indata som matchar deras markeringsvillkor. När du hovrar över en nod visas information om delningen och inmatningslistan expanderas så att de delade punkterna visas längs grenen och kursens distribution. </p> <p>Noder under ett tröskelvärde visas inte som standard. Klicka på en utökningsbar nod (indikeras av symbolen +) för att utforska en gren. Klicka på rotnoden för att återgå till den fullständiga trädvisningen. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_E800327344194A6DBF37F273D8462E2A"></a> -->

