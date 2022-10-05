---
description: Lista över filer som installerats med Insight Server och de filer som finns efter registreringen, och som körs för första gången.
title: Katalogstruktur för Insight Server
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Katalogstruktur för Insight Server{#insight-server-directory-structure}

{{eol}}

Lista över filer som installerats med Insight Server och de filer som finns efter registreringen, och som körs för första gången.

## Filer som ingår i installationspaketet {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Följande kataloger ingår i [!DNL Insight Server] installationspaket:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Katalog </th> 
   <th colname="col2" class="entry"> Beskrivning av kataloginnehåll </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Åtkomstkontroll </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> konfigurationsfil som anger en lista med åtkomstgrupper. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresser </td> 
   <td colname="col2"> Adress(er) som används för kommunikation med <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Granskning </td> 
   <td colname="col2"> Dagliga åtkomstloggar med information om alla anslutningsförsök till <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> körbara programfiler. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certifikat </td> 
   <td colname="col2"> Digitala SSL-certifikat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komponenter </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> komponentkonfigurationsfiler. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komponenter för serverbearbetning </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> komponentkonfigurationsfiler för bearbetning <span class="keyword"> Insight-servrar </span> inom <span class="keyword"> Insight Server </span> kluster. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Händelser </td> 
   <td colname="col2"> Dagliga händelseloggar som innehåller detaljerade händelsemeddelanden, inklusive felmeddelanden. Händelser som fångats in och loggats av <span class="keyword"> Insight Server </span> visas också i Windows Event Viewer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggar </td> 
   <td colname="col2"> <p>Loggfiler skapade av <span class="wintitle"> Sensor </span>(s). </p> <p>"Logs" är standardloggningskatalogen, men en alternativ katalog kan ha angetts i <span class="filepath"> communications.cfg </span> -fil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uppslag </td> 
   <td colname="col2"> Uppslagsfiler, till exempel robot- och sökmotorlistor. <span class="keyword"> Insight Server </span> måste läsa in alla uppslagsfiler i minnet. Den totala storleken på alla sökfiler som komponentkonfigurationsfilerna refererar till, plus overhead (t.ex. 12 byte per rad för <span class="filepath"> FlatFileLookup </span> filer) får inte överskrida det tillgängliga fysiska eller virtuella minnet som är tillgängligt när alla andra program har lästs in. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profiler </td> 
   <td colname="col2"> <p>Filer som är relaterade till varje profil (konfigurations-, arbetsyte- och visualiseringsfiler). Profiler fylls i med data från en datauppsättning. Datauppsättningarna innehåller händelsedata ("loggdata"); sådana data kan hämtas av installerade <span class="wintitle"> Sensorer </span>, som överförs av webbfyrar eller sidtaggar, eller indata från data warehouse. <span class="keyword"> Insikt </span> Användare med åtkomst till en viss profil får använda uppsättningen bearbetade data för den profilen samt de arbetsytor och visualiseringar som definieras i den profilen. </p> <p>Arbetsytor är arbetsytor för systemadministration eller -analys. En arbetsyta kan innehålla flera gränssnitt med olika detaljer om systemprestanda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mjukvara </td> 
   <td colname="col2"> <span class="keyword"> Insikt </span> programuppdateringar. Rapportera programuppdateringar lagras också här. </td> 
  </tr> 
 </tbody> 
</table>

## Kataloger och filer skapade efter start {#section-ef7408e8fae64454b326ec07453d4628}

Katalogerna som anges nedan skapas efter [!DNL Insight Server] registreras och körs för första gången:

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Katalog </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Läge </td> 
   <td colname="col2"> Bearbetar information som genererats av <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tillfällig </td> 
   <td colname="col2"> <p>Plats för temporära filer som används av <span class="keyword"> Insight Server </span> under upparbetning och drift. Det finns vanligtvis en fil (med namnet <span class="filepath"> temp.db </span> som standard) per fysisk enhet. </p> <p> <span class="keyword"> Insight Server </span> måste konfigureras för att skriva till den här katalogen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kalkera </td> 
   <td colname="col2"> Logg- och händelsedata om <span class="keyword"> Insight Server </span>. Användbar för felsökning. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Användare </td> 
   <td colname="col2"> Namngiven ( <span class="keyword"> Insikt </span>) användare med åtkomst till profilerna på servern. En katalog för varje auktoriserad namngiven användare skapas i katalogen Användare när användaren först kommer åt <span class="keyword"> Insight Server </span> via <span class="keyword"> Insikt </span>. Katalogen för varje namngiven användare innehåller kataloger som motsvarar alla profiler som användaren har använt på den <span class="keyword"> Insight Server </span> samt deras lokala adressfiler. </td> 
  </tr> 
 </tbody> 
</table>
