---
description: Sammanfogningsomformningen tar värden från indatafältet (vanligtvis en vektor med strängar), kombinerar dem till en enda sträng avgränsad med den angivna avgränsaren och placerar den resulterande strängen i det angivna utdatafältet.
title: Sammanfoga
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
exl-id: 75fa824b-f68d-4ec4-a75d-0f742a7bb1ba
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 1%

---

# Sammanfoga{#merge}

Sammanfogningsomformningen tar värden från indatafältet (vanligtvis en vektor med strängar), kombinerar dem till en enda sträng avgränsad med den angivna avgränsaren och placerar den resulterande strängen i det angivna utdatafältet.

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
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
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Standardvärdet som ska användas om villkoret är uppfyllt och indatavärdet inte är tillgängligt. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avgränsare </td> 
   <td colname="col2"> <p>Sträng som används för att separera de enskilda elementen i indatasträngsvektorn i den enskilda utdatasträngen. </p> <p> Om du håller ned Ctrl-tangenten och högerklickar i avgränsarparametern visas en <span class="wintitle"> Infoga</span>-meny. Den här menyn innehåller en lista med specialtecken som ofta används som avgränsare. </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> En vektor med strängvärden som kombineras till utdatasträngen. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> Namnet på utdatasträngen. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet antas en indatavektor med strängar innehålla en uppsättning produkter som har valts för inköp. Dessa produkter placeras i en enda utdatasträng och avgränsas med &quot;::&quot; (två kolon).

![](assets/cfg_TransformationType_Merge.png)

Om indatafältet x-products innehåller strängvärdena B57481, C46355 och Z97123 blir den resulterande utdatasträngen x-show-products B57481::C46355::Z97123.
