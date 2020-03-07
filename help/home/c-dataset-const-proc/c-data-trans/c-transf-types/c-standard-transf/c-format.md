---
description: Formatomformningen tar en uppsättning indata och formaterar dem för att skapa en utdatafil som matchar den angivna strukturen.
solution: Analytics
title: Format
topic: Data workbench
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Format{#format}

Formatomformningen tar en uppsättning indata och formaterar dem för att skapa en utdatafil som matchar den angivna strukturen.

Omformningen fungerar på enkla strängar eller strängvektorer och skapar utdata genom att använda det givna formatet på varje indatavärde tills alla indatavärden har omformats.

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Beskrivande namn på omformningen. Här kan du ange valfritt namn. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om omvandlingen. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor som den här omformningen används under. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Format </td> 
   <td colname="col2"> <p>En formateringssträng som används för att ange hur utdata ska se ut. </p> <p> %1% refererar till ett värde från den första indatavektorn, %2% refererar till ett värde från den andra indatavektorn och så vidare. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> <p>Fält som innehåller enkla strängar eller strängvektorer. När det gäller strängvektorer som indata blir utdata också en strängvektor som är ett resultat av att parametern <span class="wintitle"> Format</span> används för varje uppsättning indatavärden. </p> <p> <p>Obs!  Numreringen av indata börjar på 0, men numreringen av formatersättningsvärdena börjar på %1%. </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> Namnet på det fält som skapats för att innehålla resultatet av omformningen. Om indata är strängvektorer är längden på utdatasträngsvektorn längden på den längsta indatavektorn. Om vissa vektorer för indatasträngar har kortare längd används tomma strängar för deras position i formatsträngen tills längden på utdatavektorn nås. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet omvandlas två vektorer, en vektor med strängar som representerar produktkategorier och den andra en motsvarande strängvektor som representerar kvantiteten för varje köpt produkt, till en enda vektor med samma längd i form av: Produkt %1%, kvantitet %2%.

![](assets/cfg_TransformationType_Format.png)

Om indatavektorerna innehöll produktkategorier av (683, 918) och mängder av (10, 4) blir resultatet en slutlig utdatavektor som innehåller följande två strängar: (&quot;Product 683, Quantity 10&quot;, &quot;Product 918, Quantity 4&quot;).
