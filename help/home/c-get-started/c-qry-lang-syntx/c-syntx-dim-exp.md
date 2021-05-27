---
description: Dimension-uttryck används aldrig ensam, men kan användas var som helst där en dimension anropas i ett metrisk uttryck eller filteruttryck.
title: Syntax för dimensionsuttryck
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# Syntax för dimensionsuttryck{#syntax-for-dimension-expressions}

Dimension-uttryck används aldrig ensam, men kan användas var som helst där en dimension anropas i ett metrisk uttryck eller filteruttryck.

1. Understrukna ord ska anges bokstavligen i uttryckstexten.
1. Formuläret `{TEXT}?` representerar valfri text.
1. Formuläret `{TEXT}*` representerar text som kan förekomma noll eller flera gånger.
1. Formuläret `{A | B | C |...}` representerar text som består av exakt ett av de angivna alternativen, till exempel A eller B eller C...
1. Formuläret `[A,B)` representerar ett nummerintervall, från A till men inte B.

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifierare </p> </td> 
   <td colname="col2"> <p>En identifierare refererar till en namngiven dimension. Information om reglerna för juridiska identifierare finns i <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Syntax för identifierare </a>. </p> <p>Exempel: Sessions[ Session_Number = "1" ] är antalet sessioner som hade sessionsnumret "1". Sessionsnummer är en namngiven dimension som identifieraren refererar till. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Dimension) </p> </td> 
   <td colname="col2"> <p>Resultatet av (Dimension) är detsamma som resultatet av Dimensionen. Parenteser anger ordningen för åtgärder i ett uttryck. </p> <p>Exempel: Sessioner[ (Sida) = "/home" ] är antalet sessioner som besöker sidan "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tona ned efter nivå </p> </td> 
   <td colname="col2"> <p>Definierar en dimension som har samma element som dimensionen Dim, men som relaterar till andra dimensioner via dimensionsnivån. </p> <p>Ett element i den nya dimensionen avser samma nivåelement som samma element i Dim, och gäller de element i andra dimensioner som hör till någon av dessa nivåelement. </p> <p>Exempel: Sessioner[ (sida av besökare)="/hem" ] är antalet sessioner med besökare som besökt sidan "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Nivå,Grupp,N) </p> </td> 
   <td colname="col2"> <p>Definierar en dimension som har samma element som dimensionen Dim. Det tionde elementet i dimensionsnivån är relaterat till samma element i den nya dimensionen som det element i Dim som är relaterat till elementet e+Nth i Nivå, förutsatt att de tionde och e+Nth-elementen i nivån relaterar till samma element i dimensionsgruppen. </p> <p>Exempel: Page_Views[ shift(Page, Page_View, Session, 1)="/home" ] är antalet sidvyer som nästa sida som visas i samma session är "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>Liknar shift(Dim,Level,Group,N), förutom att om det finns tomma värden i dimensionen hoppas de över. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> Definierar en dimension som klassificerar element på Nivå baserat på en lista med filter. Elementen i den nya dimensionen är strängarna som anges som argument. Varje nivåelement relaterar till det första elementet i segmentdimensionen vars filter tillåter nivåelementet. Detta liknar segmentvisualiseringen. </p> <p>Exempel: segment(Visitor, "One-Time Visitors" -&gt; Visitor_Sessions = 1, "Mycket lojala besökare" -&gt; Visitor_Sessions &gt; 10, "Alla andra" -&gt; Sant) skapar en dimension som klassificerar besökare i tre grupper - engångBesökare är de som endast har en session, mycket lojala besökare är de som har fler än tio sessioner och alla andra besökare har värdet "1" Alla andra." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>Definierar en dimension vars element är intervall med siffror (med fast storlek, t.ex. [0-9], [10-19],..). Nivåelement relaterar till elementet i den bucket dim vars intervall innehåller måttvärdet för det elementet i nivån. Format är den utskriftsformatsträng som används för att formatera måttelementen. </p> <p>Exempel: Om Page_Duration_Minutes är en sidvisningsnivådimension som representerar antalet minuter som har tillbringats på varje sida, är bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5) en sessionsnivådimension som representerar antalet minuter som tillbringats i varje session. elementen är 5 minuters intervall <code>{[0-5), [5-10),...,[495-500)}</code>. </p> <p>Start är startvärdet för det första intervallet (standard: 0) och Size är intervallets storlek (standard: 1). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}* )}* ) </p> </td> 
   <td colname="col2"> <p>Definierar en dimension vars element är de givna ElementName-strängarna och är associerade med motsvarande uppsättningar Prefix-strängar. Nivåelement relaterar till elementet i prefix dim, som är associerat med det längsta prefixet som matchas av namnet på det angivna nivåelementet. Prefix som slutar med specialtecknet '$' måste matchas exakt. </p> <p>Exempel: prefix(URI, "Produkter" -&gt; ("/produkter/"), "Tjänster" -&gt; ("/tjänster/", "/products/service/"), "Garantier" -&gt; ("/products/warranty.html$", "/services/warranty.html$", "Allt annat" -&gt; ("/"))) skapar en dimension som klassificerar URI:er i de fyra listade kategorierna. Effekten på olika sidor är följande: </p> <p>/products/warranty.html går in på Garantin eftersom den matchar /products/warranty.html$-prefixet exakt. </p> <p>/products/cars/specialcar.html går in i Produkter eftersom det matchar prefixet /products/ och inte längre prefix </p> <p>/products/service/something.html går in på Tjänster eftersom det matchar prefixet /products/service/ som är längre än prefixet /products/. </p> <p>/companyinfo/aboutus.html går in i kategorin"Allt annat" eftersom det enda prefix som matchar är"/". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>latens(Level, Clip, Dim, Filter, MaxBefore, MaxAfter, FormatString) </p> </td> 
   <td colname="col2"> <p>Se <a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a"> Skapa Dimensioner för fördröjning </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product(separator {,Dim}*) </p> </td> 
   <td colname="col2"> <p>Definierar en dimension vars element är alla kombinationer ("den kartesiska produkten") av elementen i de angivna dimensionerna. Namnet på varje element skapas genom sammanfogning av motsvarande element i indatamåtten, avgränsade med den givna avgränsningssträngen. </p> <p>Om till exempel dimensionen D1 har elementen {"a", "b"} och dimensionen D2 har elementen {"x", "y"}, har kartesisk produkt("-", D1, D2) elementen {"a-x", "a-y", "b-x", "b-y"}. </p> <p>Observera att var och en av indatamåtten behandlas som om antalet dess element är nästa högre potens på två. Detta leder till att den kartesiska produkten har några "dummy"-element. När du använder Data Workbench-API:t kan dessa element redigeras, beroende på utdataformatet, eller visas som "#nnn", där nnn är elementets ordningstal (och ska ignoreras av klienten). </p> <p>Om D2 till exempel har de tre elementen {"x", "y", "z"}, behandlas det som om det hade fyra element och den kartesiska produkten hade elementen {"a-x", "a-y", "a-z", "#3", "b-x", "b-y", "b-z", "#7"}. </p> <p>Om inga dimensioner anges är resultatet en dimension med ett element, "#0", som motsvarar dimensionen Inget. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Närmaste_räkningsbar(Dim) </p> </td> 
   <td colname="col2"> <p>Avser en befintlig dimension: den närmaste räkningsbara överordnade för Dim i schemat. Närmaste countable(URI) är identisk med Page_View. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>normaliserad(Dim,Count) </p> </td> 
   <td colname="col2"> <p>Definierar ett normaliserat mått från det normala måttet Dim, med upp till Count-element. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>Definierar en dimension som har en delmängd av elementen i dimensionen Dim, vars element representerar tidssegment, till exempel dagar, veckor eller år. </p> <p>Delmängden är ett intervall runt en angiven tid, värdet för den konstanta metriska tidsmätningen, som tolkas som ett tidsvärde i sekunder sedan midnatt UTC 1 januari 1970. Intervallet innehåller Count-element, varav det sista är Offset-element efter det angivna Dim-elementet vars namn är resultatet av formatering av måttets värde med den givna FormatString-strängen. FormatString använder samma %-escape som standardversionen av C-biblioteksfunktionen. </p> <p>Om trimToData är true tas alla element i början av den resulterande dimensionen, som skulle vara före början av Dim, bort. När värdet är false kommer det alltid att finnas det exakta antalet element som anges av Count. Observera att det alltid kan finnas element i slutet av den resulterande dimensionen som inte finns i Dim. </p> <p>Valfri WeekStart, om den anges, måste vara någon av { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" }. TimeMetric ändras genom att det flyttas bakåt till den senaste förekomsten av den veckodagen. </p> <p>Exempel: Om Week har elementen { "10/03/10", "10/10/10", ..., "12/12/10" } och det inbyggda måttet As Of har värdet 1292348109 (vilket representerar en tid i mitten av 14 december, 20 010) och sedan sista n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun") definierar dimensionen med elementen { "12/12/10", "12/19/10", "12/23/10", "12/30/10" }. </p> <p>Exempel 2: Om veckodimensionen bara har elementen {"12/19/10", "12/26/10", ..., "01/30/11"} och måttet Per är som ovan, ger sista n(Vecka, Per_Av, "%m/%d/%y", 4, 0, true, "Sun") en dimension med elementen {"12/19/10", "12/23/10", "12/30/10"}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Definierar en dimension som har en delmängd av elementen i Dim, vars element representerar dagar. Delmängden är ett intervall runt en angiven tid, värdet för den konstanta metriska tidsmätningen, som tolkas som ett tidsvärde i sekunder sedan midnatt UTC 1 januari 1970. Intervallet innehåller de element som motsvarar varje dag i de nMånader som föregår den angivna tiden. Om includeThisMonth är true inkluderar intervallet även varje dag i månaden som innehåller den angivna tiden. </p> <p>FormatString anger formateringen av elementen i Dim, med "%" flyter som i standardversionen av C-biblioteksfunktionen. </p> <p>Om trimToData är true tas alla element i början av den resulterande dimensionen, som skulle vara före början av Dim, bort. När värdet är false kommer det alltid att finnas det exakta antalet element som anges av Count. Observera att det alltid kan finnas element i slutet av den resulterande dimensionen som inte finns i Dim. </p> <p>Exempel: Om Dag har elementen {"01/01/10", "01/02/10", ..., "12/31/10" } och det inbyggda värdet för As Of har värdet 1292348109 (vilket representerar en tid i mitten av 14 december 20 10) och därefter dagar i föregående månader (Day, As_Of, "%m/%d/%y", 2, false, false) kommer att ha elementen { "10/01/10", "10/02/10", ..., "11/30/10" }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>Liknar dagar i föregående månader, förutom att elementen bara motsvarar dagar i samma månad som den tid som anges av TimeMetric. Om allMonth är true kommer det att finnas ett element för varje dag i den aktuella månaden. I annat fall är det bara dagar från den första i den aktuella månaden till den dag som innehåller den angivna tiden som ingår i dimensionen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_month(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>Liknar dagar i föregående månader, förutom att elementen motsvarar dagar i månader efter, i stället för tidigare, månaden som innehåller den tid som anges av TimeMetric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, DaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>Definierar en dimension som har en delmängd av elementen i Dim, vars element representerar timmar. Delmängden är ett intervall runt en angiven tid, värdet för den konstanta metriska tidsmätningen, som tolkas som ett tidsvärde i sekunder sedan midnatt UTC 1 januari 1970. Intervallet innehåller de element som motsvarar varje timme på dagen nDaysForward efter dagen som innehåller den tid som anges av TimeMetric. </p> <p>FormatString anger formateringen av elementen i Dim, med "%" flyter som i standardversionen av C-biblioteksfunktionen. Formatsträngen ska alltid returnera en sträng som representerar midnatt i början av den angivna tiden. </p> <p>Om trimToData är true tas alla element i början av den resulterande dimensionen, som skulle vara före början av Dim, bort. När värdet är false kommer det alltid att finnas det exakta antalet element som anges av Count. Observera att det alltid kan finnas element i slutet av den resulterande dimensionen som inte finns i Dim. </p> <p>Exempel: Om Hour har elementen {"01/01/10 00:00", "01/01/10 01:00", ..., "12/31/10 23:00" } och det inbyggda As Of-måttet har värdet 1292348 109 (som representerar en tid i mitten av 14 december 2010), och sedan timmar på dagen (Timme, som_Av, "%x 00:00", 0, false) har element { "12/12/10 00:00", "12/10 01:00", ..., "12/12/10 23:00" }. </p> </td> 
  </tr> 
 </tbody> 
</table>
