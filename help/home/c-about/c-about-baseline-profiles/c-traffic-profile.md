---
description: Trafikprofilen innehåller följande mått för att identifiera besökstrafik.
title: Trafikprofilmått
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 1%

---

# Trafikprofilmått{#traffic-profile-metrics}

Trafikprofilen innehåller följande mått för att identifiera besökstrafik.

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Metrisk formel och nivå </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Första besökssida </td> 
   <td colname="col2">Formel: <span class="filepath"> Sidvyer[ingen växling(Ingen,Sidvy, Session,-1)]</span><p>Nivå: Sidvy </p></td> 
   <td colname="col3"> Antalet sessioner som angavs för webbplatsen på varje sida. Det här måttet utvärderas endast över siddimensionen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utgångshastighet </td> 
   <td colname="col2">Formel: <span class="filepath"> Avslutar/Sidvyer </span><p>Nivå: Sidvy </p></td> 
   <td colname="col3"> Procentandel sessioner som slutade webbplatsen från varje sida. Exit Rate-måttet kan bara utvärderas över siddimensionen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sista besökssida </td> 
   <td colname="col2">Formel:<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>Nivå: Sidvy </p></td> 
   <td colname="col3"> Antalet sessioner som har avslutat webbplatsen från varje sida. Det här måttet utvärderas endast över siddimensionen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Formel: <span class="filepath"> (raw(Visitors) - ((raw(Visitors) + .69)^0.5 * 1.281551 - 1.2269))*(Visitors/raw(Visitors))</span><p>Nivå: Besökare </p></td> 
   <td colname="col3"> Ett mått på det lägsta antalet möjliga besökare enligt Insight. Matematiskt anger det lägsta antalet besökare med en sannolikhet på 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Varaktighet för sidvy </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> summa (exact_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>Nivå: Sidvy </p> </td> 
   <td colname="col3"> Den genomsnittliga tiden (MM:SS) som har ägnats åt en viss sida eller grupp av sidor. Det här måttet utvärderas endast över siddimensionen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sidvisningar per session </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Page_Views/ (Sessions by Page_View) </span></p> <p>Nivå: Session </p> </td> 
   <td colname="col3"> Genomsnittligt antal sidvisningar i varje session som innehåller sidvyer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sidvisningar </td> 
   <td colname="col2">Formel: <span class="filepath"> summa(en, sidvy)</span><p>Nivå: Sidvy </p></td> 
   <td colname="col3"> Antalet sidvisningar. En sidvy är en begäran om en definierad sida (åtkomst till bilder och andra typer av filtrerat innehåll räknas inte). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Procent av sidvisningar </td> 
   <td colname="col2">Formel: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Nivå: Sidvy </p></td> 
   <td colname="col3"> Procentandel av sidvisningar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Procent av sessioner </td> 
   <td colname="col2">Formel: <span class="filepath"> Sessioner/totalt(sessioner)</span><p>Nivå: Session </p></td> 
   <td colname="col3"> Procentandel sessioner. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pct of Visitors </td> 
   <td colname="col2">Formel: <span class="filepath"> Besökare/totalt(Besökare) </span><p>Nivå: Besökare </p></td> 
   <td colname="col3"> Andelen besökare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Refererade kontaktpersoner </td> 
   <td colname="col2"> <p>Formel: Refererade_besökare/besökare </p> <p>Nivå: Besökare </p> </td> 
   <td colname="col3"> Andelen besökare som refererades till den här webbplatsen från en annan webbplats. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Refererade sessioner </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> sessioner[Referent&lt;&gt; 'Inget' och Referent&lt;&gt;'bokmärken']</span></p> <p>Nivå: Session </p> </td> 
   <td colname="col3"> Antalet sessioner som refererats till den här webbplatsen från en annan plats. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Refererade besökare </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besökare[Besökare_ Referent&lt;&gt;'Inget' och Besökare&lt;&gt;'Bokmärken']</span></p> <p>Nivå: Besökare </p> </td> 
   <td colname="col3"> Antalet besökare som hänvisas till den här webbplatsen från en annan webbplats. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kvarhållning </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> sessioner[shift(None,Ses sion,Visitor,1) = ""] / sessioner</span></p> <p>Nivå: Session </p> </td> 
   <td colname="col3"> Andelen sessioner som inte är besökarnas senaste sessioner. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessionsvaraktighet </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> (summa (Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>Nivå: Session </p> </td> 
   <td colname="col3">Den genomsnittliga tiden (MM:SS) som en besökare tillbringar i en session. <p><p>Obs! Du kan använda det här måttet med funktionen <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> Segmentexport</a>. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessioner per sidvy </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Sessioner via Page_View</span></p> <p> Nivå: Session </p> </td> 
   <td colname="col3"> Antalet sessioner som hade en sidvy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessioner </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> summa(en, session)</span></p> <p>Nivå: Session </p> </td> 
   <td colname="col3"> Antal besökssessioner. En session är en aktivitetsperiod för en besökare på en webbplats. Enskilda sessioner för varje besökare identifieras med hjälp av cookies, tidsgränser och annan heuristik. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Confidence(Sessions) * 1.281551 / Sessions</span></p> <p>Nivå: Besökare </p> </td> 
   <td colname="col3"> Ett mått på tillförlitligheten hos sessionsmåttet enligt data workbench. Matematiskt sett är det ett +/- procenttal som anger intervallet inom vilket det faktiska svaret ligger 80 % av tiden. Som tumregel ger en fördubbling av SCI80-procenten ett intervall inom vilket det faktiska svaret ligger 99 % av tiden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors))*( Visitors/raw(Visitors))</span></p> <p>Nivå: Besökare </p> </td> 
   <td colname="col3"> Ett mått på det högsta antalet möjliga besökare enligt Insight. Matematiskt anger det högsta antalet besökare med en sannolikhet på 90 %. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Formel: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitors)</span><p>Nivå: Besökare </p></td> 
   <td colname="col3"> Ett mått på tilliten hos besökarnas mått enligt Insight. Matematiskt sett är det ett +/- procenttal som anger intervallet inom vilket det faktiska svaret ligger 80 % av tiden. Som tumregel ger en fördubbling av procentvärdet för VCI80 ett intervall inom vilket det faktiska svaret ligger 99 % av tiden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besökare efter sidvy </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besökare av Page_View</span></p> <p>Nivå: Sidvy </p> </td> 
   <td colname="col3"> Antalet besökare som hade en sidvy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besökare efter session </td> 
   <td colname="col2"> <p>Formel: <span class="filepath"> Besökare via session </span></p> <p>Nivå: Session </p> </td> 
   <td colname="col3"> Antalet besökare som hade en session. </td> 
  </tr> 
 </tbody> 
</table>
