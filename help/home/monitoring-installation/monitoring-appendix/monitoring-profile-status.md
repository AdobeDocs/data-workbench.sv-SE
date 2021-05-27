---
description: Följande mått är tillgängliga för användning i data workbench Profile Status profile profile profile profile profile.
title: Dimensioner i Datans Workbench profilstatusprofil
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 0%

---

# Dimensioner i Datans Workbench profilstatusprofil{#dimensions-in-the-data-workbench-profile-status-profile}

Följande mått är tillgängliga för användning i data workbench Profile Status profile profile profile profile profile.

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Blockera</b> </td> 
   <td colname="col2"> Detta är den enda räkningsbara konfigurationen och finns som rot för alla dimensioner. Ett block kan betraktas som en server. Det använder x-trackingid-fältet. Blockets ID är en hash av servernamnet plus värdnamnet, så det kommer att finnas ungefär ett block per server och profil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Efter fördröjningsminuter</b> </td> 
   <td colname="col2"> cs-uri-query(bi) placeras i fältet x-as-of-delay-minutes och avrundas till närmaste minut. Fördröjningsminuter är en numerisk dimension som tar den sista raden från x-as-of-delay-minutes för ett block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Miljö</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(c) används för miljö-ID. Den sista raden för ett block används som värde för dimensionen. Den här enkla Dimensionen visar miljön där dina servrar körs (förutsatt att den är korrekt konfigurerad). <p>Detta kan anges i filen insight_monitor_agent.cfg </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mega-indata per minut</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(bj) används för den här dimensionen. Den sista raden för ett block används som värde för dimensionen. Om datauppsättningen är i snabb inmatning visar den numeriska Dimensionens värde den MB per minut som systemet matar in data med. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mega-byte för snabb sammanslagning per minut</b> </td> 
   <td colname="col2">Värdet cs-uri-query(bk) används för den här dimensionen. Den sista raden för ett block används som värde för dimensionen. Om datauppsättningen är i snabb sammanslagning visar den här numeriska Dimensionens värde den MB per minut som systemet sammanfogas med. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes-fält</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(bg) används för den här dimensionen. Värdet divideras med 1000 och avrundas till närmaste heltal. Den här numeriska Dimensionens värde visar mängden utrymme som används för fälten i datauppsättningen. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Värd</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(b) används för den här dimensionen. Värdet för den enkla dimensionen är sista raden för ett block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Senaste ping</b> </td> 
   <td colname="col2">x-last-ping är x-unixtime dividera med 10 (för att passa storleksbegränsningarna för numeriska dimensioner). Senaste Ping är den sista raden för ett visst block, och det representerar den senaste gången övervakningsagenten loggade systemhälsan. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Loggläsningsprocent</b> </td> 
   <td colname="col2">Värdet cs-uri-query(be) används för den här numeriska dimensionen. Det är sista raden för ett visst block. Den här dimensionen används för att beräkna hur många procent av loggarna som ska läsas. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID för bearbetningsläge</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(bb) används för den här enkla Dimensionen. Det är sista raden för ett visst block. Med ett ID för bearbetningsläge kan du se vilket bearbetningsläge systemet har (snabb inmatning, snabb sammanslagning, realtid). <p>Obs!  Dimensionen är dold och sedan återexponerad med egna värden i dimensionshanteringsläget på klientsidan. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Bearbetningen har avbrutits</b> </td> 
   <td colname="col2"> Fältet för x-bearbetning-fast skapas med olika villkor för att ange om profilen körs eller inte. Det är en enkel dimension. <p>Obs!  Denna dimension fungerar bäst när det finns ett stort antal indataloggar som ska fördelas jämnt mellan DPU:erna. Om det t.ex. bara finns en stor fil inläst per dag kan data workbench se ut som"stall" under en timme eller mer, vilket ger en falsk positiv läsning från den här dimensionen. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Profil</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(ba) används för den här enkla Dimensionen. Den här dimensionen visar namnet/namnen på de profiler som för närvarande övervakas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Källa längst bak</b> </td> 
   <td colname="col2"> Den sista raden med cs-uri-query(bl) kopieras till fältet x-source-furest-behind. I Dimensionen Enkel används sista raden för ett visst block. Den här dimensionen visar när den senaste kontakten med en datakälla inträffade. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Omformningsprocent</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(bf) används för den här numeriska dimensionen. Det är sista raden för ett visst block. Den här dimensionen används för att beräkna procentandelen av fullständig dataomvandling. <p>Obs!  Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensioner</b> </td> 
   <td colname="col2"> Timme, Dag, Vecka, Månad, Timme på dagen och Dag på veckan hämtas alla från fältet för x-tidsstämpling. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupp</b> </td> 
   <td colname="col2"> Grupperingsord som ger dig ett annat sätt att filtrera den resulterande datauppsättningen. Ange i filen insight_monitor_agent.cfg. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mätvärden</b> </td> 
   <td colname="col2"> Nedan visas mätvärden som ingår i data workbench Profile Monitoring Profile och hur de härleds. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Efter fördröjningsminuter</b> </td> 
   <td colname="col2"> Det här måttet är summan av minuterna per fördröjning för varje block och sedan dividerat med blockmåttet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Efter fördröjning i sekunder</b> </td> 
   <td colname="col2"> Detta mått är summan av sekundvärdena per fördröjning för varje block, dividerat med det totala antalet block. (Dimensionen Efter fördröjning i sekunder är inte konfigurerad utanför rutan) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Block</b> </td> 
   <td colname="col2"> Summa ett för varje block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Snabb inmatning MB per minut</b> </td> 
   <td colname="col2"> Summan av MegaBytes för snabb inmatning per minut för varje block dividerat med antalet block när MegaBytes för snabb inmatning per minut är större än noll. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Snabb sammanslagning MB per minut</b> </td> 
   <td colname="col2"> Summan av MegaBytes för snabb sammanslagning per minut för varje block dividerat med antalet block när MegaBytes för snabb sammanslagning per minut är större än noll. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>GigaBytes-fält</b> </td> 
   <td colname="col2"> Summan av fält-gigabyte för varje block dividerat med blockmått. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Senaste sidålder</b> </td> 
   <td colname="col2"> Från och med tiden minus senaste Ping-tid. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Senaste Ping-tid</b> </td> 
   <td colname="col2"> Summan av senaste Ping för varje block dividerat med block, multiplicerat med 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Loggläsning</b> </td> 
   <td colname="col2"> Om procentvärdet för loggläsning är större än noll är Loggläsning summan av procent för loggläsning för varje block, dividerat med antalet block, som alla är dividerat med 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Bearbetningen har avbrutits</b> </td> 
   <td colname="col2"> Summan av Dimensionen Bearbetning av förinställd för varje block, dividerat med värdet för block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Omformning</b> </td> 
   <td colname="col2"> Summan av omformningsprocenten för varje block dividerat med blockmåttet, när omformningsprocenten är större än noll, alla dividerat med 10. </td> 
  </tr> 
 </tbody> 
</table>
