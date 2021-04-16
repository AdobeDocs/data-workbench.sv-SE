---
description: Resursövervakarens vektor innehåller Minnesbudgetövervakaren och Antal frågor-övervakaren.
title: Resursövervakare för frågekö
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Resursövervakare för frågekö{#query-queue-resource-monitors}

Resursövervakarens vektor innehåller Minnesbudgetövervakaren och Antal frågor-övervakaren.

I följande tabell beskrivs de resursövervakningsfält som används för frågekö.

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Minnesbudgetövervakare </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Övervakar frågeminnet som används av den aktuella användargruppen. Om den aktuella användningen ligger mellan låg tröskel och hög tröskel kommer inga nya buntar att schemaläggas förrän minnesanvändningen återgår till under låg tröskel, till exempel till följd av att användaren stänger sina arbetsytor. Schemalagda buntar får växa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Högt tröskelvärde </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Det höga tröskelvärdet för minnesanvändning (byte). Om minnesanvändningen är högre än detta värde sker ingen schemaläggning och de lägsta prioriterade schemalagda klasserna är oschemalagda en åt gången under en tidsperiod, tills minnesanvändningen är lägre än detta värde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Låg tröskel </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Det låga tröskelvärdet för minnesanvändning (byte). Om värdet <span class="wintitle"> för Minnesbudgetövervakaren</span> är under det här värdet tillåts nya buntar att schemaläggas och schemalagda buntar tillåts växa. Paketen växer till exempel när en användare lägger till en visualisering på en arbetsyta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reaktionstid </p> </td> 
   <td colname="col2"> <p>double </p> </td> 
   <td colname="col3"> <p>Tidskonstanten för utjämning av uppskattad minnesanvändning. Utjämningsvärden undviker att reagera på användningstoppar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Antal frågeväljare </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Övervakar det totala antalet frågor som är schemalagda för profilen. Med den här resursövervakaren kan du schemalägga buntar om det totala antalet frågor ligger under värdet i fältet Lågt tröskelvärde. Med den här monitorn kan aktuella schemalagda buntar växa om det totala antalet frågor ligger under värdet i fältet Högt tröskelvärde. Dessutom tar den här övervakaren bort buntar med låg prioritet så att högprioriterade buntar kan schemaläggas eller växa. Den här inställningen förhindrar dock inte indelningar med en högre prioritet än vad som angetts i fältet Oberörbar prioritet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Högt tröskelvärde </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Det höga tröskelvärdet för minnesanvändning (byte). Om minnesanvändningen är högre än detta värde sker ingen schemaläggning och de schemalagda klasserna med lägst prioritet avschemaläggs en åt gången under en tidsperiod, tills minnesanvändningen är lägre än detta värde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Låg tröskel </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Det låga tröskelvärdet för minnesanvändning (byte). Om <span class="wintitle">-värdet för Minnesbudgetövervakaren</span> är under det här värdet kan nya buntar schemaläggas och schemalagda buntar kan växa. </p> </td> 
  </tr> 
 </tbody> 
</table>
