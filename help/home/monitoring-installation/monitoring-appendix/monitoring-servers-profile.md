---
description: Följande dimensioner är tillgängliga för användning i serverstatusprofilen för data workbench.
title: Dimensioner i Datans Workbench serverstatusprofil
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 0%

---

# Dimensioner i Datans Workbench serverstatusprofil{#dimensions-in-the-data-workbench-server-status-profile}

{{eol}}

Följande dimensioner är tillgängliga för användning i serverstatusprofilen för data workbench.

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Server</b> </td> 
   <td colname="col2"> Den här räkningsbara dimensionen är skapad från x-trackingid-fältet och representerar de servrar som för närvarande kör data workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Agentversion</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(af) används för den här enkla Dimensionen. Det är det sista icke-tomma värdet för en server. Detta visar byggdatum och byggtid för de versioner av övervakningsagenten som körs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>All profilåtergivning</b> </td> 
   <td colname="col2"> Fältet cs-uri-query(a) används för den här numeriska Dimensionen, det är värdet för den sista raden för en viss server, villkorat med cs-uri-query(k) är inte tomt. Den här dimensionen används för att ange om några profiler bearbetas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procentvärde för kapacitetsrad</b> </td> 
   <td colname="col2"> Fältet cs-uri-query(r) används för den här numeriska Dimensionen, det är värdet för den sista raden för en viss server, villkorat med cs-uri-query(k) är inte tomt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procent av kapacitetsstorlek</b> </td> 
   <td colname="col2"> Fältet cs-uri-query(n) används för den här numeriska Dimensionen, det är värdet för den sista raden för en viss server, villkorat med cs-uri-query(k) är inte tomt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gemensamt namn</b> </td> 
   <td colname="col2"> Fältet sc-ur-query(am) används för den här enkla Dimensionen, det är värdet för värdet Last Nonblank för en viss server. Här visas det vanliga namnet på de servrar som övervakas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentkontrollen lyckades</b> </td> 
   <td colname="col2"> Fältet cs-uri-query(v) används för den här enkla Dimensionen, det är värdet för den sista raden för en viss server. Den här dimensionen kontrollerar serverkomponenterna för att kontrollera att de fungerar som de ska. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponenter i fel</b> </td> 
   <td colname="col2"> En Crossrows-omformning tar värdet för sista raden i cs-uri-query(ao) och kopierar det till fältet x-components-in-error. I den här många-många-dimensionen visas eventuella felkomponenter på servrar som övervakas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Miljö</b> </td> 
   <td colname="col2">Värdet cs-uri-query(c) används för miljö-ID. Den sista raden för ett block används som värde för dimensionen. Den här enkla Dimensionen visar miljön där dina servrar körs (förutsatt att den är korrekt konfigurerad). <p><p>Obs! Den här dimensionen anges i insight_monitor_agent.cfg. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beräknad svep deksekunder</b> </td> 
   <td colname="col2"> Fältet för x-Estimated-sweep-dekaseconds används i den här numeriska Dimensionen. Detta är den uppskattade sveptiden för servrarna dividerat med tio (minskad upplösning för svepmätning för att göra måttet mer rimligt stort). <p><p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Värd</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(b) används för den här dimensionen. Värdet för den enkla dimensionen är sista raden för ett block. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Senaste ping</b> </td> 
   <td colname="col2"> x-last-ping är x-unixtime dividera med 10 (för att passa storleksbegränsningarna för numeriska dimensioner). Senaste Ping är den sista raden för ett visst block, och det representerar den senaste gången övervakningsagenten loggade systemhälsan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Läs in medel</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder den sista raden för en viss servers cs-uri-query(i)-värde. Den villkoras av att cs-uri-query(k) inte är tom. Denna dimension används för att beräkna den genomsnittliga belastningen på servrarna i det system som övervakas. <p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procent av minnessidfil</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder den sista raden för en viss servers cs-uri-query(o)-värde. Den villkoras av att cs-uri-query(k) inte är tom. Den här dimensionen används för att beräkna procentandelen av sidfilens minnesanvändning. <p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Totalt antal fysiska megabyte</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder den sista raden för en viss servers värde cs-uri-query(ag). Den villkoras av att cs-uri-query(k) inte är tom. <p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fysisk procent minne</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder den sista raden för en viss servers värde cs-uri-query(ag). Den villkoras av att cs-uri-query(k) inte är tom. Den här dimensionen används för att beräkna procentandelen fysiskt minnesutnyttjande för varje server. <p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procent för minnesfråga</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder den sista raden för en viss servers cs-uri-query(s)-värde. Den villkoras av att cs-uri-query(k) inte är tom. Den här dimensionen används för att beräkna procentandelen frågeminnesanvändning för varje server. <p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nätverksanslutningar</b> </td> 
   <td colname="col2"> Detta är en numerisk dimension som använder den sista raden för en viss servers cs-uri-query(q)-värde. Den villkoras av att cs-uri-query(k) inte är tom. Detta används för att visa antalet nätverksanslutningar som finns för en viss server. <p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Centisekunder för fördröjning av omröstning</b> </td> 
   <td colname="col2"> Den här dimensionen används för att beräkna avsökningsfördröjningen. Värdet cs-uri-query(m) divideras med 10 för att minska dimensionsstorleken och kopieras till fältet x-poll-latency-centiseconds. Detta är en numerisk dimension som tar den sista raden för en viss server. <p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Snabbkontrollen lyckades</b> </td> 
   <td colname="col2"> Detta är en enkel dimension som har skapats utifrån värdet cs-uri-query(g) för sista raden för en viss server. Det används för att beräkna snabbkontrollsmåtten. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Procentvärde för temporärt databasutrymme</b> </td> 
   <td colname="col2"> Den sista raden i värdet för cs-uri-query(an) kopieras till fältet x-temp-db-space-percentage. Detta är en numerisk Dimension som används för att beräkna procentandelen använt temporärt DB-utrymme på en viss server. <p>Obs! Den här dimensionen är dold eftersom den bara är användbar när den genereras till ett mått. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight Version</b> </td> 
   <td colname="col2"> Värdet cs-uri-query(ab) används för den här enkla Dimensionen. Det är det sista icke-tomma värdet för en server. Visar version(er) av data workbench-servern som körs på varje server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Grupp</b> </td> 
   <td colname="col2"> Grupperingsord som ger dig ett annat sätt att filtrera den resulterande datauppsättningen. <p>Obs! Den här dimensionen anges i insight_monitor_agent.cfg. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mätvärden</b> </td> 
   <td colname="col2"> Nedan visas mätvärden som ingår i data workbench Profile Monitoring Profile och hur de härleds. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Total kapacitet</b> </td> 
   <td colname="col2"> Detta är kapacitetsstorleksmåttet gånger två plus kapacitetsradens mått dividerat med 3. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapacitetsrad</b> </td> 
   <td colname="col2"> Detta är summan av procentsatsen för kapacitetsrader för varje server dividerat med serverns mått. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Kapacitetsstorlek</b> </td> 
   <td colname="col2"> Detta är summan av procentvärdet för kapacitetsstorlek för varje server dividerat med måttet Servrar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Komponentkontroll</b> </td> 
   <td colname="col2"> Detta är antalet servrar där lyckade komponentkontroller är lika med ett, dividerat med servern där tjänsten är DPU eller FSU, alla multiplicerat med 100 (vilket är en procentandel). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Skiva "x"</b> </td> 
   <td colname="col2"> Diskmåtten beräknas genom att summan av deras diskanvändning i procent för varje server, dividerat med serverns mått. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beräknade svepningsminuter</b> </td> 
   <td colname="col2"> Detta är summan av de beräknade summorna per sekund för svepning för varje server, dividerat med serverns mätvärde, där de beräknade summorna för svepning är större än noll, alla dividerat med 6. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Senaste Ping-tid</b> </td> 
   <td colname="col2"> Summan av senaste Ping för varje block dividerat med block, multiplicerat med 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Läs in</b> </td> 
   <td colname="col2"> Detta är summan av Load Average för varje server, dividerat med Server-måttet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Minnessidfil</b> </td> 
   <td colname="col2"> Detta är summan av procentandelen minnessidfil för varje server dividerat med serverns mått. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fysiskt minne</b> </td> 
   <td colname="col2"> Detta är summan av den fysiska procentandelen minne för varje server dividerat med serverns mått. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Minnesfråga</b> </td> 
   <td colname="col2"> Detta är summan av minnesfrågeprocenten för varje server dividerat med servermåttet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nätverksanslutningar</b> </td> 
   <td colname="col2"> Detta är summan av nätverksanslutningarna för varje server dividerat med serverns mått. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Svarstid i millisekunder</b> </td> 
   <td colname="col2"> Detta är summan av Centisekunder för fördröjning vid avsökning för varje server, dividerat med serverns mått, som alla multipliceras med 10. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Snabbkontroll</b> </td> 
   <td colname="col2"> Detta är antalet servrar där Snabbkontroll lyckades är lika med ett, dividerat med serverns mått, som alla multipliceras med 100. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Servrar</b> </td> 
   <td colname="col2"> Detta är summan av en för varje server, eller det totala antalet övervakade servrar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tillfällig DB</b> </td> 
   <td colname="col2"> Detta är summan av den tillfälliga databasens utrymmesprocent för varje server dividerat med serverns mått. </td> 
  </tr> 
 </tbody> 
</table>
