---
description: Följande dimensioner är tillgängliga för användning i den historiska profilen för data workbench.
solution: Analytics
title: Dimensioner i historikprofilen för Data Workbench
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioner i historikprofilen för Data Workbench{#dimensions-in-the-data-workbench-historic-profile}

Följande dimensioner är tillgängliga för användning i den historiska profilen för data workbench.

## Dimensioner i historikprofilen för Data Workbench {#section-96f1b64f5cb84411b630f97f227d888d}

Följande dimensioner är tillgängliga för användning i den historiska profilen för data workbench.

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Blockera</b> </td> 
   <td colname="col2">Detta är den enda räkningsbara konfigurationen, den är roten för alla dimensioner. Ett block kan betraktas som en server. Det använder x-trackingid-fältet. <p>Obs!  Blockets ID är en hash av servernamnet plus värdnamnet, så det kommer att finnas ungefär ett block per server och profil. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> Detta är en räkningsbar dimension som är inbyggd i blockräkningsfunktionen. Varje rad med data i profilen är en pingfunktion från övervakningsagenten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Varning kritisk</b> </td> 
   <td colname="col2"> Numerisk dimension som skapats utifrån värdet för cs-uri-query(ad). Den byggs på Ping-nivå och villkoras av att cs-uri-query(a) matchar "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Avisering nedåt</b> </td> 
   <td colname="col2"> Numerisk dimension som skapats från cs-uri-query(ac)-värde. Den byggs på Ping-nivå och villkoras av att cs-uri-query(a) matchar "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Varning</b> </td> 
   <td colname="col2"> Numerisk dimension som skapats från cs-uri-query(ae)-värde. Den byggs på Ping-nivå och villkoras av att cs-uri-query(a) matchar "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>All profilåtergivning</b> </td> 
   <td colname="col2"> Numerisk dimension som skapats från cs-uri-query(aa)-värde. Den är byggd på Ping-nivå och förutsätter att cs-uri-query(a) matchar "1" och cs-uriquery(k) inte är tom. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Efter fördröjningsminuter</b> </td> 
   <td colname="col2"> cs-uri-query(bi) placeras i fältet x-as-of-delay-minutes och avrundas till närmaste minut. Den byggs på Ping-nivå och villkoras av att cs-uri-query(a) matchar "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procentvärde för kapacitetsrad</b> </td> 
   <td colname="col2"> Numerisk dimension som skapats från cs-uri-query(r)-värde. Den är byggd på Ping-nivå och förutsätter att cs-uri-query(a) matchar "1" och cs-uriquery(k) inte är tom. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procent av kapacitetsstorlek</b> </td> 
   <td colname="col2"> Numerisk dimension som skapats från cs-uri-query(n)-värde. Den är byggd på Ping-nivå och förutsätter att cs-uri-query(a) matchar "1" och cs-uriquery(k) inte är tom. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentkontrollen lyckades</b> </td> 
   <td colname="col2"> Enkel dimension som skapats från cs-uri-query(v)-värde. Den byggs på Ping-nivå och villkoras av att cs-uri-query(a) matchar "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponenter i fel</b> </td> 
   <td colname="col2"> cs-uri-query(ao) delas av avgränsaren "|" och kopieras till fältet x-components-in-error. Många till många dimensioner har skapats från felfältet x-components-in. Byggd på Ping-nivå. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Detaljerade kontroller sekunder</b> </td> 
   <td colname="col2"> Numerisk dimension som skapats från cs-uri-query(l)-värde. Den byggs på Ping-nivå och förutsätter att cs-uri-query(k) inte är tom. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Detaljerad kontroll lyckades</b> </td> 
   <td colname="col2"> Enkel dimension som skapats utifrån värdet för cs-uri-query(k). Den byggs på Ping-nivå och villkoras av att cs-uri-query(a) matchar "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimension GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc) kopieras till fältet x-dimension-gigabytes. Fältet x-dimension-gigabytes är användbart för den här enkla dimensionen, som är villkorad av cs-uri-query(a) som matchar "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procent av disken x som används</b> </td> 
   <td colname="col2"> Dessa numeriska dimensioner konfigureras utifrån värdena för cs-uri-query(ah, ai, aj, ak, al). De byggs på Ping-nivå och konditioneras i cs-uri-query(a) matchar "1" och cs-uri-query(k) är inte tomma. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beräknad svep deksekunder</b> </td> 
   <td colname="col2"> Fältet för x-estimated-sweep-dekaseconds används i den här numeriska dimensionen. Detta är den uppskattade sveptiden för servrarna dividerat med tio (minskad upplösning för svepmätning för att göra måttet mer rimligt stort). <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mega-indata per minut</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(bj) används för den här dimensionen. Den sista raden för ett block används som värde för dimensionen. Om datauppsättningen är i snabb inmatning visar den här numeriska dimensionens värde den MB per minut som systemet matar in data med. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mega-byte för snabb sammanslagning per minut</b> </td> 
   <td colname="col2">Värdet cs-uri-query(bk) används för den här dimensionen. Den sista raden för ett block används som värde för dimensionen. Om datauppsättningen är i snabb sammanslagning visar den här numeriska dimensionens värde den MB per minut som systemet sammanfogas med. <p><p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes-fält</b> </td> 
   <td colname="col2">Värdet cs-uri-query(bg) används för den här dimensionen. Värdet divideras med 1000 och avrundas till närmaste heltal. Den här numeriska dimensionens värde visar mängden utrymme som fälten i datauppsättningen använder. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupp</b> </td> 
   <td colname="col2"> Enkel dimension som skapats på Ping-nivå från värdet för cs-uri-query(x). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Värd</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(b) används för den här dimensionen. Värdet för den enkla dimensionen är sista raden för ett block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Senaste ping</b> </td> 
   <td colname="col2"> x-unixtime-fältet kopieras till x-last-ping och divideras med 10 för att minska kardinaliteten. Den numeriska dimensionen byggs på blocknivå och använder x-last-ping-fältet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Läs in medel</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder den sista raden för en viss servers cs-uri-query(i)-värde. Den villkoras av att cs-uri-query(k) inte är tom. Denna dimension används för att beräkna den genomsnittliga belastningen på servrarna i det system som övervakas. <p><p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Loggläsningsprocent</b> </td> 
   <td colname="col2">Värdet cs-uri-query(be) används för den här numeriska dimensionen, som har skapats på Ping-nivå. Den här dimensionen används för att beräkna hur många procent av loggarna som ska läsas. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procent av minnessidfil</b> </td> 
   <td colname="col2"> Det här är en numerisk dimension som använder cs-uri-query(o)-värde som skapats på Ping-nivå. Den villkoras av att cs-uri-query(k) inte är tom och cs-uri-query(a) matchar "1". Den här dimensionen används för att beräkna procentandelen av sidfilens minnesanvändning. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Totalt antal fysiska megabyte</b> </td> 
   <td colname="col2">Detta är en numerisk dimension som använder värdet cs-uri-query(ag), som skapats på Ping-nivå. Den villkoras av att cs-uri-query(k) inte är tom och cs-uri-query(a) matchar "1". <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fysisk procent minne</b> </td> 
   <td colname="col2">Detta är en numerisk dimension som använder värdet cs-uri-query(ag), som skapats på Ping-nivå. Den villkoras av att cs-uri-query(k) inte är tom och cs-uri-query(a) matchar "1". Den här dimensionen används för att beräkna procentandelen fysiskt minnesutnyttjande för varje server. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procent för minnesfråga</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder värdet för cs-uri-query (cs) på Ping-nivå. Den villkoras av att cs-uri-query(k) inte är tom och cs-uri-query(a) matchar "1". Den här dimensionen används för att beräkna procentandelen frågeminnesanvändning för varje server. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nätverksanslutningar</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder värdet cs-uri-query(q) som har skapats på Ping-nivå. Den villkoras av att cs-uri-query(k) inte är tom och cs-uri-query(a) matchar "1". Detta används för att visa antalet nätverksanslutningar som finns för en viss server. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Utdatarader</b> </td> 
   <td colname="col2"> cs-uri-query(bh)-värdet divideras med 100000 och kopieras till fältet x-output-rows för att minska dimensionens storlek. X-output-rows används i en numerisk dimension som är byggd på Ping-nivå och som är villkorad att cs-uri-query(a) matchar "2". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping-typ-ID</b> </td> 
   <td colname="col2"> Enkel dimension som skapats med cs-uri-query(a)-värdet på Ping-nivå. Detta visar vilken typ av Ping som spelades in. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisekunder för fördröjning av omröstning</b> </td> 
   <td colname="col2">Värdet cs-uri-query(m) divideras med 10 för att minska dimensionsstorleken och kopieras till fältet x-poll-latency-centiseconds. Det här är en numerisk dimension som skapats på Ping-nivå, med villkoret att cs-uri-query(k) inte är tom, och cs-uri-query(a) matchar "1"/ Den här dimensionen används för att beräkna fördröjningen för avsökningen. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID för bearbetningsläge</b> </td> 
   <td colname="col2"> cs-uri-query(bb)-värdet används för den här enkla dimensionen, som har skapats på Ping-nivå. Det är villkorat att cs-uri-query(bb) inte är tom och att cs-uri-query(a) matchar "2" Bearbetningsläge-ID gör att man kan se vilket bearbetningsläge systemet är i (Fast Input, Fast Merge, Real Time). <p>Obs!  Dimensionen är dold och sedan återexponerad med egna värden i dimensionshanteringsläget på klientsidan. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(ba) används för den här enkla dimensionen, det skapas på Ping-nivå. Den här dimensionen visar namnet/namnen på de profiler som för närvarande övervakas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Snabbkontrollsekunder</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(h) används för den här numeriska dimensionen. Den byggs på Ping-nivå och villkoras av att cs-uri-query(a) matchar "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Snabbkontrollen lyckades</b> </td> 
   <td colname="col2"> Detta är en enkel dimension som har skapats från värdet cs-uri-query(g) som har skapats på Ping-nivå. Det används för att beräkna snabbkontrollsmåtten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procent av realtidsbearbetning</b> </td> 
   <td colname="col2"> Numerisk dimension med cs-uri-query(t)-värdet som är skapat på Ping-nivå. Det är villkorat att cs-uri-query(a) matchar "1". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Källa längst bak</b> </td> 
   <td colname="col2"> Enkel dimension som bygger på bl-värdet (cs-uri-query) som skapats på Ping-nivå. Den här dimensionen visar när den senaste kontakten med en datakälla inträffade. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procentvärde för temporärt databasutrymme</b> </td> 
   <td colname="col2">Numerisk dimension som skapats med cs-uri-query(an)-värdet, som skapats på Ping-nivå. Det är villkorat att cs-uri-query(k) inte är tom och cs-uri-query(a) matchar "1". Den används för att beräkna procentandelen använt temporärt DB-utrymme på en given server. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Omformningsprocent</b> </td> 
   <td colname="col2">Värdet cs-uri-query(bf) används för den här numeriska dimensionen. Den är byggd på Ping-nivå. Den här dimensionen används för att beräkna procentandelen av fullständig dataomvandling. <p><p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench-version</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(ab) används för den här enkla dimensionen. Den är byggd på Ping-nivå och villkorad att cs-uri-query(ab) inte är tom och cs-uri-query(a) matchar "1". Visar version(er) av data workbench-servern som körs på varje server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench Version - större</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(ab) delas och det större versionsvärdet kopieras till fältet x-insight-version-major. Det är en enkel dimension som skapats på Ping-nivå och som villkorats att x-insight-version-major inte är tom och cs-uri-query(a) matchar"1". </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->

