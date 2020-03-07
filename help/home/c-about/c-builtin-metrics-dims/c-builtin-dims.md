---
description: Data workbench innehåller inbyggda dimensioner.
solution: Analytics
title: Inbyggda dimensioner
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Inbyggda dimensioner{#built-in-dimensions}

Data workbench innehåller inbyggda dimensioner.

I följande tabell visas de tillgängliga inbyggda dimensionerna för data workbench:

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namn </th> 
   <th colname="col2" class="entry"> Detaljer </th> 
   <th colname="col3" class="entry"> Nivå </th> 
   <th colname="col4" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ingen </td> 
   <td colname="col2"> Härledd </td> 
   <td colname="col3"> Ej tillämpligt </td> 
   <td colname="col4">Har ett enda element "" som relaterar till alla element av alla dimensioner. Att utvärdera ett mätresultat över Inget är som att utvärdera det utan dimension. <p>Filtret <span class="filepath"> [None=""]</span> motsvarar <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> En (dold) </td> 
   <td colname="col2"> Numeriskt </td> 
   <td colname="col3"> Ej tillämpligt </td> 
   <td colname="col4">Elementet "1", som också har ett ordvärde <span class="filepath"> = 1</span>, gäller alla element med alla dimensioner. Enkeldimensionen används vanligtvis för att konstruera antal med den här syntaxen: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

