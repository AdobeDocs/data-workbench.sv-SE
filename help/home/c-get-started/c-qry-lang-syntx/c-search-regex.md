---
description: Data workbench använder reguljära uttryck (regex) för sök- och sorteringsåtgärder.
title: Reguljära uttryck
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 0%

---

# Reguljära uttryck{#regular-expressions}

Data workbench använder reguljära uttryck (regex) för sök- och sorteringsåtgärder.

I fältet **[!UICONTROL Search]** kan du utföra en sökning efter satsen &quot;re:&quot; med vanliga uttryck, till exempel:

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

Ytterligare vanliga reguljära uttryck kan också användas för att skapa mer komplexa söksträngar. Reguljära uttryck används i alla sökfält för Data Workbench, inklusive frågans entitetspaneler.

Mer detaljerad information finns i [reguljära uttryck](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).
