---
description: Med en tidsdimension kan du skapa en uppsättning periodiska eller absoluta mått för lokal tid (t.ex. Dag, Veckodag, Timme på dagen, Reservationstid osv.) baserat på ett tidsstämpelfält som du anger för parametern Indatatid (1970 epok).
solution: Analytics
title: Tidsdimensioner
topic: Data workbench
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tidsdimensioner{#time-dimensions}

Med en tidsdimension kan du skapa en uppsättning periodiska eller absoluta mått för lokal tid (t.ex. Dag, Veckodag, Timme på dagen, Reservationstid osv.) baserat på ett tidsstämpelfält som du anger för parametern Indatatid (1970 epok).

När du definierar tidsdimensioner kan du också välja en annan dag än måndag som ska användas som början av en vecka genom att ange parametern Startdag för vecka. Du kan definiera mer än en uppsättning tidsdimensioner i datauppsättningen så länge som dimensionerna har olika namn.

Tidsdimensionerna definieras av följande parametrar:

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
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
   <td colname="col1"> Dimensioner </td> 
   <td colname="col2"> <p>Du kan ange dimensionsnamn för följande perioder: </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> Dag </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> Veckodag </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> Timme </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> Timme på dagen </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> Månad </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> Vecka </li> 
     </ul> </p> <p> De namn du anger här är de namn som visas i dimensionsmenyer och i visualiseringar i data workbench. Om du lämnar namnet på en tidsdimension tomt skapas inte dimensionen i datauppsättningen. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dold </td> 
   <td colname="col2"> Avgör om dimensionen visas i gränssnittet för data workbench. Som standard är den här parametern inställd på false. Om dimensionen till exempel bara ska användas som bas för ett mätresultat, kan du ställa in den här parametern på true för att dölja dimensionen från data workbench-visningen. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indatatid (1970 epok) </td> 
   <td colname="col2"> <p>Namnet på det tidsstämpelfält som ska användas som indata. </p> <p> <p>Obs!  Fältets värden måste representera antalet sekunder sedan 1 januari 1970, 00:00:01. Om indatatiden inte är en giltig tid (1970 till 2037) misslyckas omvandlingsprocessen och data workbench-servern genererar ett fel. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överordnad </td> 
   <td colname="col2"> Namnet på den överordnade dimensionen. Alla räkningsbara dimensioner kan vara en överordnad dimension. För webbdata är den överordnade sessionen Session. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Veckostartdag </td> 
   <td colname="col2"> <p>Den dag som ska användas som första dag i en vecka. </p> <p> Den här parametern påverkar dimensionen Vecka, Dag i veckan och eventuella dimensioner för rapporteringstid som definieras i antal veckor. </p> </td> 
   <td colname="col3"> Mon </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet skapas en uppsättning tidsdimensioner baserade på det användardefinierade indatafältet x-time-1970. Tidsdimensionerna för uppsättningen heter&quot;Sessionstid&quot;. Eftersom det överordnade elementet för varje dimension är sessionsdimensionen, motsvarar varje element i tidsdimensionerna den tid då en session påbörjades. Parametern Startdag för vecka anger att varje vecka i dimensionen Vecka börjar på måndag.

![](assets/cfg_Transformation_Dim_TimeDim.png)

