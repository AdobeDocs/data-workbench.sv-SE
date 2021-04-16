---
description: Den delade omformningen delar upp en sträng i en vektor med delsträngar baserat på ett visst avgränsningstecken.
title: Dela
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
exl-id: ea85b095-1306-4938-906d-35d421db6c98
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 1%

---

# Dela{#split}

Den delade omformningen delar upp en sträng i en vektor med delsträngar baserat på ett visst avgränsningstecken.

[!DNL Split] är särskilt användbart när du vill extrahera enskilda värden från en samling värden som är kopplade till ett enda URI-frågenamnvärde.

<table id="table_C97DA4E45DA844FAB8D61AABA22FF809"> 
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
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om omvandlingen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor som den här omformningen används under. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avgränsare </td> 
   <td colname="col2"> <p>Sträng som används för att separera indatasträngen till delsträngar. Måste vara ett enda tecken långt. </p> <p> Om du håller ned Ctrl-tangenten och högerklickar i avgränsarparametern visas en Infoga-meny. Den här menyn innehåller en lista med specialtecken som ofta används som avgränsare. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Namnet på det fält vars värde delas för att skapa vektorn för utdatasträngen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> Namnet på utdatafältet. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Tänk dig en webbplats där produkter som köpts av en kund listas som en del av cs-uri-query-värdet när bekräftelsesidan som är kopplad till ett lyckat köp är tillgänglig. Följande är ett exempel på en sådan sträng:

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

Fältet cs-uri-stam används för att avgöra om sidan som efterfrågas av loggposten är bekräftelsesidan. Koderna för produkterna som kunden har köpt listas som kommaavgränsade värden för prod_selected i cs-uri-frågan. Du kan använda [!DNL Split]-omformningen för att extrahera den här informationen genom att dela produktkoderna vid kommatecken om värdet för cs-uri-stam matchar värdet som anges i [!DNL String Match]-villkoret. Se [Strängmatchning](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). I följande omformning beskrivs lösningen på problemet.

![](assets/cfg_TransformationType_Split.png)

Här är utdatafältet x-produkter, vilket skulle användas för att skapa den önskade utökade dimensionen som mappar inköpta produkter till de sessioner under vilka köpet gjordes.
