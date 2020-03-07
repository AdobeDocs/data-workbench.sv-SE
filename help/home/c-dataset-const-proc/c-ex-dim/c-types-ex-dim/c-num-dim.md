---
description: En numerisk dimension består av ordnade numeriska element och har en 1:N-relation med dess överordnade räkningsbara dimension.
solution: Analytics
title: Numeriska dimensioner
topic: Data workbench
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Numeriska dimensioner{#numeric-dimensions}

En numerisk dimension består av ordnade numeriska element och har en 1:N-relation med dess överordnade räkningsbara dimension.

Du kan tänka dig en numerisk dimension som en representation av de numeriska egenskaperna för elementen i den överordnade dimensionen. Om du till exempel arbetar med webbdata kan du definiera den numeriska dimensionen Sessionsintäkt, som definierar ett intäktsbelopp i dollar för varje session i sessionsdimensionen. Varje session har ett enda intäktsbelopp, men flera sessioner kan ha samma intäktsbelopp. Därför har dimensionen Sessionsintäkt en-till-många-relation med sessionsdimensionen.

Numeriska dimensioner används ofta för att definiera mått som summerar värden, räknar förekomster av ett villkor eller letar upp ett minimum- eller maximivärde. Ett mått med namnet&quot;Intäkter&quot; kan till exempel definieras med dimensionen Sessionsintäkter: sum(Session_Revenue, Session). Definieras på det här sättet ger intäktsmåttet det totala intäktsbeloppet för de valda sessionerna.

Numeriska dimensioner kan inte vara överordnade dimensioner.

Numeriska dimensioner definieras med följande parametrar:

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
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
   <td colname="col1"> Klippvärden </td> 
   <td colname="col2"> Sant eller falskt. Anger om indatavärdet (efter operation) ska beskäras till värden mellan Min och Max. Om klippvärdena är true beskärs värdet till det intervallet. Om Clip Values är false returneras inget värde för elementet i den överordnade dimensionen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Noteringar om den utökade dimensionen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor under vilka indatafältet bidrar till att skapa den numeriska dimensionen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fast storlek </td> 
   <td colname="col2"> Sant eller falskt. Styr antalet element i en dimension (kardinalitet). Om true inkluderas alla element från Min till Max i dimensionen. Om värdet är false växer dimensionens storlek när värden läggs till. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dold </td> 
   <td colname="col2"> Avgör om dimensionen visas i gränssnittet för data workbench. Som standard är den här parametern inställd på false. Om dimensionen till exempel bara ska användas som bas för ett mätresultat, kan du ställa in den här parametern på true för att dölja dimensionen från data workbench-visningen. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> <p>Värdet som ska användas med den angivna åtgärden eller det indatavärde som du vill räkna förekomster för. </p> <p> Om det här fältet är en vektor med strängar utförs utvärderingen för varje element i vektorn. En vektor med längden 3 och operationen COUNT lägger alltså till 3 i antalet. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min </td> 
   <td colname="col2"> Lägre gräns för det slutliga dimensionsresultatet. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max </td> 
   <td colname="col2"> Övre gräns för det slutliga dimensionsresultatet. </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Förskjutning </td> 
   <td colname="col2"> Se Skala i den här tabellen. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Åtgärd </td> 
   <td colname="col2"> <p>Tillgängliga åtgärder är följande: </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> ANTAL: Det totala antalet icke-tomma värden i <span class="wintitle"> indatafältet</span> över alla loggposter som uppfyller dimensionens villkor används. Om <span class="wintitle"> inmatningsfältet</span> är ett vektorfält räknas det totala antalet icke-tomma värden i varje loggpost. </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> FÖRSTA ICKE-BLANK: Det första icke-tomma indatavärdet används, oavsett om det kommer från den första loggposten eller inte. Om <span class="wintitle"> indata</span> är ett vektorfält används den första raden i vektorn för den aktuella loggposten. Om värdet inte är ett tal används inget värde. </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> FÖRSTA RADEN: Värdet för den första loggposten som är relaterad till det överordnade dimensionselementet används, även om indata är tomma. Om <span class="wintitle"> indata</span> är ett vektorfält används den första raden i vektorn för den aktuella loggposten. Om värdet är tomt eller inte är ett tal, eller om den relevanta loggposten inte uppfyller dimensionens villkor, används inget värde. </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> SENASTE NONBLANK: Det sista icke-tomma indatavärdet används, oavsett om det kommer från den sista loggposten eller inte. Om <span class="wintitle"> indata</span> är ett vektorfält används den första raden i vektorn för den aktuella loggposten. Om värdet inte är ett tal används inget värde. </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> SISTA RADEN: Värdet för den sista loggposten som hör till det överordnade dimensionselementet används, även om indata är tomma. Om <span class="wintitle"> indata</span> är ett vektorfält används den första raden i vektorn för den aktuella loggposten. Om värdet är tomt eller inte är ett tal, eller om den relevanta loggposten inte uppfyller dimensionens villkor, används inget värde. </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> SUM: Summan av alla numeriska värden i fältet <span class="wintitle"> Indata</span> över alla loggposter som uppfyller dimensionens villkor används. Om det inte finns några sådana loggposter eller om inga numeriska värden hittas, används det numeriska värdet 0. </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">MIN eller MAX: Det minsta eller högsta numeriska värdet som hittas i fältet <span class="wintitle"> Indata</span> för alla loggposter som uppfyller dimensionens villkor används. Om det inte finns några sådana loggposter eller numeriska värden används inget värde. </li> 
     </ul> </p> <p> <p>Obs!  Du bör ange en åtgärd för att se till att dimensionen definieras som tänkt. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överordnad </td> 
   <td colname="col2"> Namnet på den överordnade dimensionen. Alla räkningsbara dimensioner kan vara en överordnad dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skala </td> 
   <td colname="col2"> <p>För att ge dimensionens ordningstal omformas resultatet av Operation enligt följande: </p> <p> (scale * input) + offset </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Om [!DNL Operation] inte ger något värde, eller [!DNL Clip Values] är false och värdet inte är mellan [!DNL Min] och [!DNL Max]är inget element i den numeriska dimensionen relaterat till elementet i den överordnade dimensionen.

I det här exemplet illustreras definitionen av en numerisk dimension med händelsedata som samlats in från webbplatstrafiken. Den här numeriska dimensionen, med namnet&quot;Ad View Counter&quot;, räknar antalet gånger som besökaren ser en annons under en viss session. Förutsättningen är att alla annonsresurser begärs från webbservern med ad= som en del av cs-uri-frågan. I det här exemplet är antalet gånger (COUNT) som besökaren får en annons det givna värdet, inte det faktiska värdet i fältet.

![](assets/cfg_Transformation_Dim_Numeric.png)

