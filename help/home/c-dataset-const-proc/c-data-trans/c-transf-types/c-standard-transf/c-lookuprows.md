---
description: Omvandlingen LookupRows söker efter andra loggposter med samma spårnings-ID och ställer in värdet för utdatafältet till värdet för ett visst fält i indataraden.
title: Uppslagsrader
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
exl-id: caa9a311-b056-4fe8-bb11-1605cc690375
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---

# Uppslagsrader{#lookuprows}

Omvandlingen LookupRows söker efter andra loggposter med samma spårnings-ID och ställer in värdet för utdatafältet till värdet för ett visst fält i indataraden.

Eftersom [!DNL LookupRows]-omformningen utför sin sökning på loggposter och inte på sökfiler, liknar den [!DNL CrossRows]-omformningen. Se [Korsrader](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

För att [!DNL LookupRows]-omformningen ska fungera måste data sorteras i tid och grupperas med spårnings-ID:t i källdata. Därför fungerar [!DNL LookupRows] bara när den definieras i filen [!DNL Transformation.cfg] eller i en [!DNL Transformation Dataset Include]-fil.

Kom ihåg följande när du granskar parameterbeskrivningarna i följande tabell:

* Utdataraden är den datarad som omformningen arbetar på vid en given tidpunkt.
* Indatarader är alla andra datarader (före, efter eller inklusive utdataraden) vars värden i indatafältet fungerar som indata för omformningen.

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col2"> Begränsar omvandlingens utdata till vissa loggposter. Om villkoret inte uppfylls för en viss loggpost ändras inte fältet i utdataradsparametern. Indata kan fortfarande användas för att påverka andra loggposter. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indatavillkor </td> 
   <td colname="col2">Accepterar indata för omformningen från endast vissa indatarader. Om villkoret <span class="wintitle"> Indata</span> inte uppfylls för en viss indatarad, ignoreras indatafältet från den raden och påverkar inte andra utdatarader. Utdatafältet från den raden ändras dock fortfarande enligt det angivna villkoret. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata för radnyckel </td> 
   <td colname="col2"> Namnet på det fält som ska användas som nyckel för indataraderna. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indataradsvärde </td> 
   <td colname="col2"> Namnet på det fält i indataraden vars värde kopieras till fältet i utdataradsparametern om alla villkor uppfylls. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Åtgärd </td> 
   <td colname="col2"> <p>En åtgärd som, för varje utdatarad, tillämpas på alla indatarader som uppfyller alla villkor som definieras av parametrarna <span class="wintitle"> Input</span> Condition och Input Row Key Input för att skapa en utdatafil: 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> FIRST returnerar värdet för fältet i Indataradens värdeindataparameter från den första matchande indataraden i data (inte den första matchande raden efter utdataraden). </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST returnerar fältets värde i Indataradens värdeindataparameter från den sista indataraden i data (inte den sista matchande raden före utdataraden). </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nyckelindata för utdatarad </td> 
   <td colname="col2"> Namnet på det fält som ska användas som nyckel för utdataraden. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdataradsvärde </td> 
   <td colname="col2">Namnet på det fält i utdataraden vars värde kopieras från fältet i indataradsparametern om alla villkor uppfylls. Alla utdatarader med samma x-trackingid- och <span class="wintitle">-utdataradnyckelindata </span>värden har samma <span class="wintitle">-utdataradsvärde</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Indata-, indata- och indataradsparametrarna definierar tillsammans uppslagsfilen för varje spårnings-ID, medan parametrarna Indata på utdataraden, Indata på utdataraden och Villkor styr vad som slås upp i filen och vilket värde som lagras i fältet som anges av utdata för radvärde.

Om du vill förstå hur omvandlingen fungerar bättre kan du titta på följande kontur:

* För varje utdatarad som uppfyller villkoret och som har en utdataradnyckelinmatning som inte är tom:

   * Hitta den första eller sista inmatningsraden så att

      * inmatningsraden uppfyller inmatningsvillkoret, och
      * x-trackingid för indataraden är lika med x-trackingid för utdataraden, och
      * Indataradens inmatningsradnyckel är lika med utdataradens inmatningsradnyckel.

* och ange utdataradens utdataradvärde som indataradens indataradvärde.

Att tänka på för [!DNL LookupRows]

* Tomma nyckelvärden matchar aldrig något. Även om det finns indatarader med tomma nycklar och icke-tomma värden som matchar [!DNL Input Condition], kommer en [!DNL Output Row Key Input] av &quot;&quot; alltid att generera [!DNL Output Row Value Output] av &quot;&quot;.

* Om det inte förbjuds av [!DNL Input Condition] kan en rad slås upp om dess [!DNL Input Row Key Input]- och [!DNL Output Row Key Input]-värden är desamma.

Om du har flera nyckelvärden kan du kombinera dem med en [!DNL Format]-omformning (se [Format](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)) innan du använder en [!DNL LookupRows]-omformning.

Anta att du har en webbplats med en registreringssida för husdjur, där namnet och rasen anges, och en senare&quot;köpleksak&quot;-sida där endast namnet på djuret används. Du vill kunna länka husdjursnamnet till den husdjursras som anges på registreringssidan. Om du vill göra det kan du skapa följande [!DNL LookupRows]-omformning:

![](assets/cfg_TransformationType_LookupRows.png)

Låt oss analysera det här exemplet med föregående kontur:

* För varje utdatarad som uppfyller ett värde som inte är tomt är cs-uri-query(petname):

   * Hitta den sista inmatningsraden så att

      * indataraden innehåller ett värde som inte är tomt för cs-uri-query(petbreed), och
      * x-trackingid för indataraden är lika med x-trackingid för utdataraden, och
      * värdet för cs-uri-query(petname) för indataraden är lika med värdet för cs-uri-query(petname) för utdataraden,

* och ange värdet för x-pet-raden för utdataraden till värdet för cs-uri-query(petbreed) för indataraden.

I [!DNL LookupRows]-omvandlingen används husdjursnamnet (nyckeln) för att se till att husdjursrasen är kopplad till både husdjursregistreringen och köpa leksakssidor så att du kan analysera leksaker som köpts för varje djurras, även för besökare med flera husdjur.
