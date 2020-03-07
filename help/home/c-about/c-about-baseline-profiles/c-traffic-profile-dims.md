---
description: Trafikprofilen innehåller följande mått som hjälper till att identifiera besöksåtgärder.
solution: Analytics
title: Trafikprofildimensioner
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trafikprofildimensioner{#traffic-profile-dimensions}

Trafikprofilen innehåller följande mått som hjälper till att identifiera besöksåtgärder.

Dimensionerna i följande tabell definieras i omformningsdatauppsättningen och innehåller filer i mappen Traffic\Dataset\Transformation directory.

| Namn | Typ | Nivå | Beskrivning |
|---|---|---|---|
| Dag | Enkel | Session | Dagen för sessionens första loggpost. |
| Veckodag | Enkel | Session | Veckodag för den första loggposten i en session. |
| Exakt sidvaraktighet (dold) | Numeriskt | Sidvy | Längden i millisekunder av sidvyn mätt genom att subtrahera tiden för nästa sidvy från tidpunkten för sidvyn. Den exakta längden för den sista sidvyn i en session är alltid 0. |
| Timme | Enkel | Session | Timmen på den första loggposten i en session. |
| Timme på dagen | Enkel | Session | Timme på dagen för den första loggposten i en session. |
| Månad | Enkel | Session | Månad för den första loggposten i en session. |
| Sidvy | Inventerbar | Session | En loggpost eller&quot;Händelsedatapost&quot; som uppfyller villkoren för sidvisning. |
| Referent | Enkel | Session | Den andra nivådomänen för referenten för den första loggposten i sessionen (eller Ingen om det är en intern referensdomän). |
| Session | Inventerbar | Besökare | En period av närliggande aktiviteter som en besökare relaterar till. Den avgränsas av en 30-minuters inaktivitetsperiod och en extern referensdomän eller en maximal 48-timmars sessionstid. Både dessa tidsgränser och den uppsättning domäner som betraktas som interna kan konfigureras i [!DNL Transformation.cfg] filen. |
| URI | Enkel | Sidvy | URI-stammen för en sidvy. URI-dimensionen kan definieras om med omformningarna ReplaceURI, PrependURI och AppendURI. |
| Besökare | Inventerbar | Ej tillämpligt | Ett unikt värde för x-trackingid. Motsvarar vanligtvis en unik webbläsare om beständiga cookies används. x-trackingid kan i övrigt baseras på IP-nummer eller någon annan unik identifierare, till exempel x.509-namn. |
| Vecka | Enkel | Session | Veckan för den första loggposten i en session. |

Dimensionerna i följande tabell definieras i Dimensionskatalogen i Trafikprofilen:

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col03" class="entry"> Nivå </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Webbläsare </td> 
   <td colname="col2"> Enkel </td> 
   <td colname="col03"> Besökare </td> 
   <td colname="col3"> Den typ av användaragent som används av besökaren, inklusive versionsnumret (till exempel MSIE 6.0.) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Typ av webbläsare </td> 
   <td colname="col2"> Enkel </td> 
   <td colname="col03"> Besökare </td> 
   <td colname="col3"> Den typ av användaragent som används av besökaren (till exempel MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sökmotor </td> 
   <td colname="col2"> Enkel </td> 
   <td colname="col03">Session <p>FÖRSTA RADEN </p></td> 
   <td colname="col3"> Den första sökmotorn i en besökares session när en besökare har sökt från en namngiven sökmotor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nästa URI </td> 
   <td colname="col2"> Härledd (ShiftDim baserad på URI-dimension) </td> 
   <td colname="col03"> Sidvy </td> 
   <td colname="col3"> URI:n för nästa URI efter den valda URI:n. Den härledda dimensionen används för att utföra analyser av vad besökare gör efter en given URI. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OneTime vs Repeat </td> 
   <td colname="col2"> Härledd (SegmentDim baserat på upprepningsbesökares och engångsbesökares mått) </td> 
   <td colname="col03"> Besökare </td> 
   <td colname="col3"> Typ av besökare: en gång eller upprepa. Engångsbesökare har bara haft en session på webbplatsen, medan återkommande besökare har haft mer än en session. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sida </td> 
   <td colname="col2"> Härledd (RenameDim baserat på URI-dimension) </td> 
   <td colname="col03"> Sidvy </td> 
   <td colname="col3"> Namnet på varje sida som besöktes under en session. Till att börja med är varje sidas namn detsamma som URI:n, men kan ändras för enklare tolkning. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referent </td> 
   <td colname="col2"> Ärvs från den inbyggda referensdimensionen </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Domännamnet på den andra nivån för den webbplats som först refererade en session till webbplatsen (som anges av besökarens webbläsare). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sökfras </td> 
   <td colname="col2"> Enkel </td> 
   <td colname="col03">Session <p>FÖRSTA RADEN </p></td> 
   <td colname="col3"> Den första sökfrasen i en besökares session som den skickas av en sökmotor när en besökare har sökt från en namngiven sökmotor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sökterm </td> 
   <td colname="col2"> Många-till-många </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Varje sökterm som skickas av en sökmotor när en besökare har en klickfrekvens från en namngiven sökmotor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessionsvaraktighet </td> 
   <td colname="col2"> Härledd (MetricDim baserat på det exakta måttet för sidvaraktighet) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Sessionens varaktighet i steg om 30 sekunder. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessionsnummer </td> 
   <td colname="col2"> Enkel </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Antalet gånger som en besökare har besökt webbplatsen. Första gången besökarna har till exempel sessionsnumret 1, andra gången besökarna har sessionsnumret 2 osv. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessionssidvyer </td> 
   <td colname="col2"> Härledd (MetricDim baserat på måttet för sidvyer) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Antalet sidvyer i en session. Om du t.ex. väljer "3" i dimensionen Vyer för sessionssidor väljs alla sessioner med exakt tre sidvyer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sökmotor </td> 
   <td colname="col2"> Enkel </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Domännamnet på den andra nivån för den första webbplatsen som är en namngiven sökmotor som refererade en besökare till webbplatsen under en session (som anges av besökarens webbläsare). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tidsdimensioner </td> 
   <td colname="col2"> Enkel </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Den timme, dag, timme på dagen, vecka, veckodag, månad, kvartal eller år då en session påbörjades. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tidsrapporteringsdimensioner </td> 
   <td colname="col2"> Härledd (dimensionerna LastN och Rename baseras på inbyggda tidsdimensioner) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Dimensioner inklusive Dagar sedan, Dagar i förra månaden, Dagar i förra veckan, Dagar i den här månaden, Dagar i den här veckan, Dagens timmar, Timmar i går, Senaste 12 månaderna, Senaste två månaderna, Senaste två veckorna, Senaste 24 timmarna, Senaste 3 månaderna, Senaste fyra veckorna, Senaste 6 månaderna, Senaste 7 dagarna, Senaste 7 dagarna och I dag 8 veckor, senaste 9 månaderna, förra månaden, förra veckan, månader sedan, den här månaden, den här veckan, den här veckan, den här och de senaste 14 dagarna, den här och de senaste 6 månaderna, den här och de senaste 8 veckorna, Idag, Dagsrapportering, Idag och de senaste 30 dagarna, Vecka sedan och i går är ett bekvämt sätt att skapa en arbetsyta eller rapport som alltid visar en del av data i datauppsättningen. Var och en baseras på när en session påbörjades. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Ärvs från den inbyggda Dimension-URI:n </td> 
   <td colname="col03"> Sidvy </td> 
   <td colname="col3"> URI:n för varje sida som visas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besökarsidvyer </td> 
   <td colname="col2"> Härledd (MetricDim baserat på måttet för sidvyer) </td> 
   <td colname="col03"> Besökare </td> 
   <td colname="col3"> Antalet sidvisningar hittills för en besökare. Om du t.ex. väljer "3" i sidvisningsdimensionen för besökare markeras alla besökare med exakt tre sidvisningar i alla sessioner. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besökarreferent </td> 
   <td colname="col2"> Ärvs från den inbyggda dimensionsreferenten </td> 
   <td colname="col03"> Besökare </td> 
   <td colname="col3"> Domännamnet på den andra nivån för den webbplats som först refererade en besökare till webbplatsen för sin första session (som anges av besökarens webbläsare). </td> 
  </tr> 
 </tbody> 
</table>

