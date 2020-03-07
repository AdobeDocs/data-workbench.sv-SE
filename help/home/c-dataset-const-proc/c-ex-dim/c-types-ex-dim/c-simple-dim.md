---
description: En enkel dimension har en 1:N-relation med dess överordnade räkningsbara dimension.
solution: Analytics
title: Enkla dimensioner
topic: Data workbench
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Enkla dimensioner{#simple-dimensions}

En enkel dimension har en 1:N-relation med dess överordnade räkningsbara dimension.

En enkel dimension är alltid underordnad en räkningsbar dimension. Du kan tänka dig en enkel dimension som en representation av en egenskap för elementen i dess överordnade dimension. Om du till exempel arbetar med webbdata kan du definiera dimensionen för besökarreferenten, som är en enkel dimension med en överordnad dimension för Visitor. Den representerar den första HTTP-referenten för varje besökare i dimensionen Besökare. Varje besökare i besökardimensionen har bara en besökarreferent, men många besökare kan ha samma besökarreferent. Därför har dimensionen för besökarrefererenten en-till-många-relation till besökardimensionen.

Enkla dimensioner definieras av följande parametrar:

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> Beskrivande namn på dimensionen så som den visas i data workbench. Dimensionsnamnet får inte innehålla ett bindestreck (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Noteringar om den utökade dimensionen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor under vilka relationen mellan överordnad och inmatningsfältets värde ska skapas. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dold </td> 
   <td colname="col2"> Avgör om dimensionen visas i gränssnittet för data workbench. Som standard är den här parametern inställd på false. Om dimensionen till exempel bara ska användas som bas för ett mätresultat, kan du ställa in den här parametern på true för att dölja dimensionen från data workbench-visningen. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Värdefältet som är relaterat till den överordnade dimensionen (överordnad). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Läs in fil </td> 
   <td colname="col2"> <p>Valfritt. En fil med tillgängliga värden för relationen. Du använder en inläsningsfil när något av följande gäller: </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> Värdena har en specifik sorteringsordning som du vill behålla i data workbench-visningen. Du kan till exempel skapa en kvartsdimension vars element (årets kvartal) alltid visas i kronologisk ordning. </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> Du vill skapa platshållare för värden som kanske inte hittas i data men som måste visas i data workbench-visningen. </li> 
     </ul> </p> <p> Om ett värde som inte finns i filen påträffas läggs det till i slutet av värdena när det visas i data workbench. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Åtgärd </td> 
   <td colname="col2"> <p>Tillgängliga åtgärder är följande: </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> FÖRSTA ICKE-BLANK: Det första icke-tomma indatavärdet används, oavsett om det kommer från den första loggposten eller inte. Om indata är ett vektorfält används den första raden i vektorn för den aktuella loggposten. </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> FÖRSTA RADEN: Värdet för den första loggposten som är relaterad till det överordnade dimensionselementet används, även om indata är tomma. Om indata är ett vektorfält används den första raden i vektorn för den aktuella loggposten. Om värdet är tomt eller inte är ett tal, eller om den relevanta loggposten inte uppfyller dimensionens villkor, används inget värde. </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> SENASTE NONBLANK: Det sista icke-tomma indatavärdet används, oavsett om det kommer från den sista loggposten eller inte. Om indata är ett vektorfält används den första raden i vektorn för den aktuella loggposten. </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> SISTA RADEN: Värdet för den sista loggposten som hör till det överordnade dimensionselementet används, även om indata är tomma. Om indata är ett vektorfält används den första raden i vektorn för den aktuella loggposten. Om värdet är tomt eller inte är ett tal, eller om den relevanta loggposten inte uppfyller dimensionens villkor, används inget värde. </li> 
     </ul> </p> <p> <p>Obs!  Om åtgärden inte ger något värde eller ett tomt värde för en viss loggpost, kommer motsvarande element i den överordnade dimensionen att relatera till elementet "Inget" för den enkla dimensionen. </p> </p> <p> Du bör ange en åtgärd för att se till att dimensionen definieras som tänkt. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överordnad </td> 
   <td colname="col2"> Namnet på den överordnade dimensionen. Alla räkningsbara dimensioner kan vara en överordnad dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet illustreras definitionen av en enkel dimension med händelsedata som samlats in från webbplatstrafiken och en inläsningsfil.

Ta ett exempel på en undersökning av webbplatsbesökarnas favoritscout-cookies. En webbsida hämtar den här rösten och returnerar den till webbservern i namnvärdespar som favoritcookie. Endast en röst per besökare räknas, men besökarna kan ändra sig och rösta igen om de vill. Det här är en 1:N-relation: en besökare kan ha många röster, men varje röst är endast kopplad till en besökare. Därför är dimensionens överordnade besökare (endast en röst per besökare) och operationen är LAST ROW (så att de kan ändra sig och rösta igen).

Platshållare måste finnas för alla typer av cookies så att cookie-typer som inte får några röster visas i data workbench-skärmen. Därför har en inläsningsfil definierats som innehåller listan med cookie-typer som kan väljas. Den här filens innehåll, som har sparats i en fil med namnet [!DNL cookietypes.txt], ser ut ungefär så här:

Djurskatter

Caramel Designs

Lemon Pastry Creams

Jordnötsmönster

Kortkommandon

Tunna spetsar

Den sista dimensionen definieras enligt följande:

![](assets/cfg_Transformation_Dim_Simple.png)

