---
description: Tabell som definierar parametrarna för användargruppen.
solution: Analytics
title: Användargrupper för frågekö
topic: Data workbench
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Användargrupper för frågekö{#query-queue-user-groups}

Tabell som definierar parametrarna för användargruppen.

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Namn </p> </td> 
   <td colname="col2"> <p>string </p> </td> 
   <td colname="col3"> <p>Ett användardefinierat namn på användargruppen, till exempel analytiker. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profiler </p> </td> 
   <td colname="col2"> <p>vektor </p> </td> 
   <td colname="col3"> <p>Anger en principtyp. Högerklicka för att välja Standardprincip eller Dagligt schema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardprincip </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>En standardprincip säkerställer att användare med låg prioritet flyttas uppåt i kön och schemaläggs, även om användare med högre prioritet går in i kön. Du kan lägga till flera profiler av samma typ i en grupp och deras effekt är kumulativ. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Prioritetsgräns:</b> Gränsen över vilken prioriteten inte ökas. Högsta prioritetsvärde. Du kan använda det här värdet om du vill behålla prioriteter som genereras av den här principen i ett visst intervall (till exempel så att prioriteter för en annan grupp alltid är högre eller så att de inte stiger över prioriteten Ej berörbart. </li> 
     </ul> </p> <p> <b>Standardpolicysteg</b> </p> <p>Inställningarna för stegvis ökning för standardregeln ökar prioriteten för ett frågebunt allt eftersom tiden går. Detta medför inte att buncherna måste schemaläggas, men du kan använda dessa inställningar för att prioritera användare som har väntat länge. Parametrarna som står i kö påverkar frågor som är i kö (t.ex. parkerade på grund av otillräckliga resurser för att slutföra dem). De schemalagda parametrarna påverkar frågor som besvaras. Prioriteten för en fråga ökar med det tal som anges i fälten för öknings- och ökningsintervall: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Ökning i kö:</b> Anger prioritetsökningen per uppdatering som står i kö. Den här inställningen ser till att användare med låg prioritet flyttas upp i schemaläggningskön. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Ökningsintervall i kö:</b> Anger antalet sekunder mellan uppdateringar när de står i kö. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Schemalagd ökning:</b> Anger prioritetsökningen per uppdatering när den är schemalagd. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Schemalagt ökningsintervall:</b> Anger antalet sekunder mellan uppdateringar när de är schemalagda. <p> <p>Obs!  Om du ställer in öknings- och intervalluppdateringshastigheterna högre för buntar som står i kö än för schemalagda buntar kan det orsaka oscillation. (Anta till exempel att du anger värdet 100 för Ökning i kö och 0 för Ökningsintervall i schemalagt läge, och att värdet 1 för Ökningsintervall i kö är 1 och att Prioriteten för oberörbart är hög. Om två frågebuntar kommer in med en basprioritet på 0, och det inte finns tillräckligt med resurser för att köra båda frågorna samtidigt, schemaläggs en av dem. Efter en sekund har frågan som inte var schemalagd en prioritet på 100 och föregriper den som var schemalagd. Efter ytterligare två sekunder har den som förväntades nu prioriteten 200, och de två switcharna placeras igen. Ingen av frågorna avslutas eftersom den fråga som beräknas föregås varannan sekund så att den andra frågan kan köras.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Princip för dagligt schema </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Gör att du kan ändra prioriteten vid specifika tidpunkter på dagen. Det här schemat är användbart för automatiserade klienter, till exempel <span class="wintitle"> Report Server</span>, och när användare av systemet bor i olika tidszoner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ändringar </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Högerklicka för att lägga till en schemalagd prioritetsändring. Ändringstiden är den tidpunkt på dagen då ändringen sker. Formatet är timme:minut AM/PM. Om AM eller PM inte anges används militär tid. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prioritetsgräns </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Det högsta prioritetsvärdet som är resultatet av en ändring. Prioritetsändring är det belopp som läggs till prioriteten. Värdet 0 återgår till standardprioritet. Alla andra värden ger standardprioriteten plus det här talet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användare </p> </td> 
   <td colname="col2"> <p>vektor </p> </td> 
   <td colname="col3"> <p>Visar de användare som är medlemmar i gruppen. </p> <p> <b>Namn:</b> Användarens namn så som det visas i fältet Gemensamt namn i användarens certifikat. </p> <p> <b>Extra prioritet:</b> Ger ytterligare prioritet till användargruppens basprioritet för att fastställa startprioriteten för den användaren. </p> </td> 
  </tr> 
 </tbody> 
</table>

