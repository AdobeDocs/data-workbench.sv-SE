---
description: För att underlätta statistikarbetet tillhandahåller Data Workbench tre statistiska mått i visualiseringen av den guidade analysen.
title: Statistikåtgärder
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
exl-id: 166ff98b-d531-4b31-897e-0c7fedbd2f4d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Statistikåtgärder{#statistical-measures}

{{eol}}

För att underlätta statistikarbetet tillhandahåller Data Workbench tre statistiska mått i visualiseringen av den guidade analysen.

>[!NOTE]
>
>Även om matematik kan hjälpa er att bedöma korrelationen i era data, måste även sammanhanget runt data beaktas.

* **Chi Sq p** är ett test av statistisk signifikans som kontrollerar utseendet på bockmarkeringen i visualiseringen. Matematiskt sett är det en sannolikhet att vi kan avvisa nollhypotesen, där det anges att skillnaderna mellan de två grupperna kan förklaras med slumpmässiga variationer. Om Chi Sq p-värdet i stort är mindre än nästan 100 % kan vi bortse från korrelationen oavsett dess uppmätta styrka (vilket beskrivs i följande avsnitt av U-statistik och V-statistik).
* **U-statistik** är ett mått på den statistiska korrelationens styrka. Matematiskt sett kommer det från en gren av matematik som kallas informationsteori och är nära besläktad med begreppet om ömsesidig information mellan de två gruppernas utdelningar. Alternativt kan man tänka sig att en grupp är komprimerad med ett optimalt kodningsschema för den andra gruppen. I stort sett fungerar denna åtgärd mycket bra när det gäller en dimension med många element som innehåller få besökare. Måttet varierar från 0 (svag) till 1 (stark).
* **V-statistik** är också ett mått på den statistiska korrelationens styrka. Matematiskt sett är det relaterat till den välkända Cramerns V-statistik, som endast skiljer sig genom ett normaliseringssteg som är avsett att förbättra måttets symmetri i förhållande till markeringsinvertering. I praktiken fungerar denna åtgärd relativt bra med många typer av dimensioner och är kopplad till en vanlig statistisk åtgärd. Måttet varierar från 0 (svag) till 1 (stark).

>[!NOTE]
>
>U- och V-statistiken valdes ut för att komplettera varandra, och var och en justerades för att identifiera typer av korrelationer som den andra kanske inte svarar lika mycket på.

Om du använder den här visualiseringen som guide kan du lägga till andra visualiseringar på arbetsytan för att få bättre insikt i dina data baserat på urvalet.

Följande [!DNL Site] exemplet innehåller ett stolpdiagram som visar sessioner för dagar i januari, februari, mars och april. Observera att en dag i januari är markerad.

![](assets/vis_GuidedAnalysis_withVis.png)

Visualiseringen av den guidade analysen i arbetsytans nedre vänstra hörn visar att dimensionen Sessionsnummer ger användbar information om den valda dagen.

Genom att undersöka diagrammet med fältet Sessionsnummer i det nedre högra hörnet av arbetsytan ser du att data för Sessionsnummer 2 är mycket lägre än prestandatestet. Därför kan vi dra slutsatsen att det var färre sessioner den valda dagen än vanligt, som en procentandel. Om du vill visa ett stapeldiagram för någon av dimensionerna som listas i visualiseringen av den guidade analysen, väljer du bara dimensionen genom att klicka med musen.
