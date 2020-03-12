---
description: Statistikpratbubblor mäter meningsfulla relationer för att identifiera dolda möjligheter och variabler av intresse, vilket ger mer avancerade datautvinningsfunktioner i målgruppsklustring och poängsättning av besökarrespons.
solution: Analytics
title: Statistiska bildtexter
topic: Data workbench
uuid: 04911ac4-bc3f-4813-800b-087d9668a782
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Statistiska bildtexter{#statistical-callouts}

Statistikpratbubblor mäter meningsfulla relationer för att identifiera dolda möjligheter och variabler av intresse, vilket ger mer avancerade datautvinningsfunktioner i målgruppsklustring och poängsättning av besökarrespons.

Statistiska hänvisningar utökar algoritmerna så att fler typer av data kan korreleras, t.ex. binomialvariabler (ja/nej, 0/1 eller köpare/icke-köpare) som korreleras med räkningsbara värden (besök, order eller nedladdningar).

Så här lägger du till statistiska hänvisningar:

1. Högerklicka på måttrubriken i en tabell.
1. Markera **[!UICONTROL Statistics]** och markera eller avmarkera bockorna för varje inställning. Alla i Bildtext är markerade som standardinställning.

   ![](assets/statistical_callouts.png)

Bildtexten kan returnera statistiska värden som tagits med i datauppsättningens kolumner.

<table id="table_B2A4F9D5938D4756A81ACF6F4D77E63D">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Beräkning </th>
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Antal </td>
   <td colname="col2"><p>Returnerar antalet rader i en datauppsättning. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Maximal </td>
   <td colname="col2"><p> Identifierar det maximala måttvärdet för alla element i dimensionen. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Minimum </td>
   <td colname="col2"><p> Identifierar det minsta måttvärdet för alla element i dimensionen. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Medel </td>
   <td colname="col2"><p> Medelvärdet är det aritmetiska medelvärdet av måtten för elementen i dimensionen, beräknat som totalsumman dividerat med antalet (summa/antal). </p></td>
  </tr>
  <tr>
   <td colname="col1"> Standardavvikelse </td>
   <td colname="col2"> Standardavvikelsen visar hur mycket variation som finns från det förväntade medelvärdet. En lägre standardavvikelse visar datapunkterna nära medelvärdet. En högre standardavvikelse visar att datapunkterna är spridda över ett stort värdeintervall. </td>
  </tr>
  <tr>
   <td colname="col1"> Totalt </td>
   <td colname="col2"><p> Returnerar den totala summan av måttvärdena. </p></td>
  </tr>
  <tr>
   <td colname="col1"> Varians </td>
   <td colname="col2"><p> Ett mått på avvikelsen för måttvärdena från måttets medelvärde för den dimensionen. Det är lika med kvadraten av standardavvikelsen. </p></td>
  </tr>
 </tbody>
</table>
