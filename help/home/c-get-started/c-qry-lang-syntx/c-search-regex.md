---
description: Data workbench använder reguljära uttryck (regex) för sök- och sorteringsåtgärder.
solution: Analytics
title: Reguljära uttryck
topic: Data workbench
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Reguljära uttryck{#regular-expressions}

Data workbench använder reguljära uttryck (regex) för sök- och sorteringsåtgärder.

I **[!UICONTROL Search]** fältet kan du utföra en sökning efter satsen &quot;re:&quot; med vanliga uttryck, till exempel:

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> metatecken </th> 
   <th colname="col2" class="entry"> description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>. (punkt) </p> </td> 
   <td colname="col2"> <p>Matchar ett enskilt tecken, till exempel: <span class="filepath"> re:x.z </span> matchar "xyz" eller "xxz". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>* (stjärna) </p> </td> 
   <td colname="col2"> <p>Matchar ett eller flera tecken, till exempel: <span class="filepath"> re:Z* </span> matchar"ZZZ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? (jokertecken) </p> </td> 
   <td colname="col2"> <p>Matchar 0 eller 1 av föregående uttryck för att framtvinga minimal matchning, till exempel: <span class="filepath"> xy?z </span> matchar "xy" och "xyz". </p> </td> 
  </tr> 
 </tbody> 
</table>

Ytterligare vanliga reguljära uttryck kan också användas för att skapa mer komplexa söksträngar. Reguljära uttryck används i alla sökfält i Data Workbench, inklusive frågans entitetspaneler.

Se detaljerad information i [reguljära uttryck](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).