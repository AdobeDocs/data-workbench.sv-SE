---
description: En många-till-många-dimension har en många-till-många-relation med sin överordnade räkningsbara dimension.
solution: Analytics
title: Många-till-många-dimensioner
topic: Data workbench
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Många-till-många-dimensioner{#many-to-many-dimensions}

En många-till-många-dimension har en många-till-många-relation med sin överordnade räkningsbara dimension.

Du kan tänka dig en många-till-många-dimension som en representation av en uppsättning värden för varje element i dess överordnade dimension. Sökfrasen för många-till-många-dimensionen är till exempel en dimension på sessionsnivå (den har en överordnad session). Den representerar uppsättningen sökfraser som är associerade med varje session i sessionsdimensionen. En enda sökfras kan användas i ett valfritt antal sessioner, och en enda session kan innehålla noll eller flera sökfraser. Därför har sökfrasdimensionen en många-till-många-relation med sessionsdimensionen.

Många-till-många-dimensioner definieras av följande parametrar:

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
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
   <td colname="col2"> Beskrivande namn på dimensionen så som den visas för användaren i data workbench. Dimensionsnamnet får inte innehålla ett bindestreck (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Noteringar om den utökade dimensionen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor under vilka relationen mellan det överordnade fältet och inmatningsfältets värde ska skapas. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dold </td> 
   <td colname="col2"> Avgör om dimensionen visas i gränssnittet för data workbench. Som standard är den här parametern inställd på false. Om dimensionen till exempel bara ska användas som bas för ett mätresultat, kan du ställa in den här parametern på true för att dölja dimensionen från data workbench-visningen. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> <p>Värdet som är relaterat till den överordnade dimensionen (överordnad). Om det här fältet är en vektor med strängar har varje element i vektorn en egen relation till den överordnade. </p> <p> <p>Obs!  Om indatavärdet för varje loggpost för ett element i den överordnade dimensionen är tomt kommer inget element i många-till-många-dimensionen att relatera till det elementet i den överordnade dimensionen. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överordnad </td> 
   <td colname="col2"> Namnet på den överordnade dimensionen. Alla räkningsbara dimensioner kan vara en överordnad dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet illustreras definitionen av en många-till-många-dimension med händelsedata som samlats in från webbplatstrafiken. Denna många-till-många-dimension med namnet&quot;Vald produkt&quot; relaterar sessioner till de produkter som köpts av besökaren under den sessionen. Fältet med x-produkter innehåller en vektor med värden, som var och en är kopplad till en sidvy, som i sin tur är kopplad till en session.

![](assets/cfg_Transformation_Dim_ManytoMany.png)

Genom att skapa en sådan omvandling kan du skapa en visualisering i data workbench som visar relationen mellan den valda produktdimensionen och antalet sessioner som involverar varje produkt.
