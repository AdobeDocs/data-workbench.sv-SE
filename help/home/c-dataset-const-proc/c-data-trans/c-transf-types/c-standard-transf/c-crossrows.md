---
description: Precis som för andra omformningar tillämpas CrossRows-omformningen på datarader (loggposter) i loggkällorna.
title: Korsrader
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
exl-id: 321f986e-44a9-454c-9311-0ae37a11a088
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 0%

---

# Korsrader{#crossrows}

{{eol}}

Precis som för andra omformningar tillämpas CrossRows-omformningen på datarader (loggposter) i loggkällorna.

För varje datarad får omformningen det angivna indatafältets värde, utför en uppsättning bearbetningssteg och registrerar resultatet i det utdatafält som du anger. När [!DNL CrossRows] omformningen fungerar på en datarad (den här raden kallas utdatarad), och tar hänsyn till att raden plus en eller flera andra datarader (de här raderna kallas indatarader) som är kopplade till samma spårnings-ID. För ett visst spårnings-ID baseras därför värdet för utdatafältet för varje utdatarad på värdena i indatafältet för en eller flera indatarader.

Omformningen innehåller flera villkor och begränsningar som gör att du kan begränsa indataraderna för omformningen. Du kan uttrycka dessa begränsningar i villkoren för servern med data workbench (se [Villkor](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)), ett intervall med indatarader i förhållande till utdataraden eller ett intervall med tider i förhållande till utdataradens tid. För de indatarader som uppfyller omformningens villkor och begränsningar kan du använda en åtgärd (till exempel SUM) som bestämmer värdet för utdatafältet.

>[!NOTE]
>
>För att arbeta [!DNL CrossRows] för omformning krävs att data ordnas i tid och grupperas med spårnings-ID:t i källdata. Därför [!DNL CrossRows] fungerar bara när det definieras i [!DNL Transformation.cfg] eller i en [!DNL Transformation Dataset Include] -fil.

Kom ihåg följande när du granskar parameterbeskrivningarna i följande tabell:

* Utdataraden är den datarad som omformningen arbetar på vid en given tidpunkt.
* Indatarader är alla andra datarader (före, efter eller inklusive utdataraden) vars värden i indatafältet fungerar som indata för omformningen. Indataraderna styrs av parametrarna Indatavillkor, Nyckel, Radstart, Radslut, Tidsstart och Tidsslut.

<table id="table_152851484AFF4C50AF736DC62FAA43E3"> 
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
   <td colname="col2"> Begränsar omvandlingens utdata till vissa loggposter. Om villkoret inte uppfylls för en viss loggpost ändras inte fältet i utdataparametern. Indata kan fortfarande användas för att påverka andra loggposter. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Namnet på fältet från indataraden som ska användas som indata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indatavillkor </td> 
   <td colname="col2"> Accepterar indata för omformningen från endast vissa indatarader. Om indatavillkoret inte uppfylls för en viss indatarad, ignoreras indatafältet från den raden och påverkar inte andra utdatarader. Utdatafältet från den raden ändras dock fortfarande enligt det angivna villkoret. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nyckel </td> 
   <td colname="col2"> <p>Valfritt. Namnet på fältet som ska användas som nyckel. </p> <p> Om en tangent anges begränsas indataraderna för en given utdatarad till det sammanhängande blocket med rader med samma nyckelvärde som utdataraden. Den här begränsningen är utöver alla andra begränsningar som har placerats på indataraderna av andra parametrar i <span class="wintitle"> Korsrader</span> omformning. </p> <p> Om du till exempel arbetar med webbdata och gör fältet x-session-key (som har ett unikt värde för varje session) till nyckeln, begränsas indataraderna för omformningen till de rader som har samma x-session-nyckelvärde som utdataraden. Därför bör du endast ta hänsyn till indatarader som representerar sidvyer som inträffar under samma session som utdataraden. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Åtgärd </td> 
   <td colname="col2"> <p>En åtgärd som, för varje utdatarad, tillämpas på alla indatarader som uppfyller alla villkor som definieras av parametrarna Indatavillkor, Nyckel, Radbörjan, Radslut, Starttid och Sluttid för att skapa en utdatafil: 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> ALL tar alla värden i indatafältet från indataraderna och skickar dem som en vektor. </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM tolkar värdena i indatafältet från indataraderna som tal och summerar dem. </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> MED FÖRSTA RADEN matas indatafältets värde ut från den första indataraden. </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> LAST ROW returnerar värdet för indatafältet från den sista indataraden. </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> Namnet på utdatafältet. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rad början/radslut </td> 
   <td colname="col2"> <p>Valfritt. Anger ett intervall med indatarader i förhållande till utdataraden. Värdet "0" för radbörjan utesluter till exempel alla rader före utdataraden. Radstartvärdet "1" utesluter också utdataraden. Vanliga intervall är: 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> Börja 0: Den här raden och alla efterföljande rader. </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> Börja 1: Alla efterföljande rader. </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> Slut 0: Den här raden och alla tidigare. </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> Slut -1: Alla föregående rader. </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> Begin -1, End -1: Föregående rad. </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> Början 1, slut 1: Nästa rad. </li> 
     </ul> </p> </td> 
   <td colname="col3"> Alla rader </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Starttid/sluttid </td> 
   <td colname="col2"> <p>Valfritt. Anger ett tidsintervall i förhållande till tiden för utdataraden. Ett tidsslut på 30 minuter innehåller till exempel alla rader som äger rum inom 30 minuter efter utdataraden. En tidsbörjan på -30 minuter innehåller alla rader som äger rum inom 30 minuter före utdataraden. </p> <p> Tillgängliga tidsenheter är dagar, veckor, timmar, minuter, ms (millisekunder), fästingar (100 nanosekunder) och ns (nanosekunder). </p> </td> 
   <td colname="col3"> Alla gånger </td> 
  </tr> 
 </tbody> 
</table>

The [!DNL CrossRows] omformningen i det här exemplet används på rader med webbdata för att för varje sidvy hitta tidpunkten för nästa sidvy. För att vi vet det [!DNL CrossRows] används endast under datauppsättningens omformningsfas och dataraderna sorteras efter besökare (varje besökare har ett unikt spårnings-ID) och tid.

Indatafältet, x-timestamp, används bara för indatarader där x-is-page-view-fältet är ifyllt (vilket anger att dataraden representerar en sidvy). Fältet x-session-key (som har ett unikt värde för varje session) anges för Key-parametern. Indataraderna (loggposter) för omformningen är därför begränsade till det sammanhängande blocket med rader som har samma värde för x-session-key som utdataraden. Med andra ord, för att kunna användas för omformningen måste en indatarad representera en sidvy som inträffar under samma session som sidvyn i utdataraden. Den första radåtgärden hämtar värdet för utdatafältet från den första indataraden som uppfyller [!DNL Input] Villkor och har samma x-session-nyckelvärde som utdataraden.

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] körs en viss tid i förhållande till storleken på indata plus storleken på utdata. Det innebär att för åtgärderna SUM, FIRST ROW och LAST ROW är det inte mindre effektivt än andra omformningar. För ALL är situationen mer komplex eftersom det går att konfigurera [!DNL CrossRows] att mata ut en datamängd för varje datarad (loggpost) som är proportionerlig till det totala antalet rader (loggposter) för ett visst spårnings-ID.
