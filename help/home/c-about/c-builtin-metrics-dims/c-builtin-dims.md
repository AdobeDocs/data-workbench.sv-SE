---
description: Data workbench innehåller inbyggda dimensioner.
title: Inbyggda Dimensioner
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 7%

---

# Inbyggda Dimensioner{#built-in-dimensions}

{{eol}}

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
   <td colname="col4">Har ett enda element "" som relaterar till alla element av alla dimensioner. Att utvärdera ett mätresultat över Inget är som att utvärdera det utan dimension. <p>The <span class="filepath"> Filter [Inget=""]</span> motsvarar <span class="filepath"> [Sant]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> En (dold) </td> 
   <td colname="col2"> Numeriskt </td> 
   <td colname="col3"> Ej tillämpligt </td> 
   <td colname="col4">Elementet "1", som också har ett ordningstal <span class="filepath"> = 1</span>, relaterar till alla element av alla dimensioner. Enkeldimensionen används vanligtvis för att konstruera antal med den här syntaxen: <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
