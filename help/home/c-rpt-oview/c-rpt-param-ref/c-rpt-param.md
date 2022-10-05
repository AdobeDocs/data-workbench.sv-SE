---
description: Information om parametrar för Report.cfg.
title: Parametrar för Report.cfg
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2348'
ht-degree: 1%

---

# Parametrar för Report.cfg{#report-cfg-parameters}

{{eol}}

Information om parametrar för Report.cfg.

Provet [!DNL Report.cfg] visas i [Konfigurera rapportuppsättningen](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) innehåller endast de parametrar som ingår i [!DNL Report.cfg] som standard. Följande tabell innehåller beskrivningar av alla tillgängliga [!DNL Report.cfg] filparametrar.

Om du behöver lägga till ytterligare parametrar i en [!DNL Report.cfg] måste du göra det med en textredigerare. Anvisningar om hur du gör detta, inklusive exempel på hur du definierar varje parameterpost, finns i [Redigera befintliga Report.cfg-filer](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

>[!NOTE]
>
>Parametrarna i den här tabellen visas i alfabetisk ordning. När du öppnar [!DNL Report.cfg] i Data Workbench visas vektorerna i alfabetisk ordning följt av de enskilda parametrarna i alfabetisk ordning.

<table id="table_F55E925EA34F43B6832788BB6878BB4A">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Parameter </th>
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Varningströskel </td>
   <td colname="col2"> <p><i>Valfritt</i>. Den här parametern gäller endast för rapporter med mätningsindikatorer. Antal mätningsindikatorer som måste visas i kalkylbladet innan en varningsrapport skickas. </p> <p>Om bara ett mått övervakas i kalkylbladet för mätindikatorn anger du tröskelvärdet till 1. Rapporten genereras när måttet i bladet utvärderas till en upp-/nedpil eller ett X. Om mer än ett mätvärde övervakas i rapporten kan du välja antalet mätindikatorer som måste utvärderas till en upp-/nedpil eller ett X innan rapporten genereras. Om till exempel två mätvärden övervakas:
     <ul id="ul_A64E8A2306B14371A233D372B956F64D">
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">Om tröskelvärdet är 1 genereras rapporten om något av värdena i bladet utvärderas till en upp-/nedpil eller ett X. </li>
      <li id="li_DA4EF4984880483DA48322D9D57B9240">Om tröskelvärdet är 2 måste båda värdena utvärderas till en upp-/nedpil eller ett X innan rapporten genereras. </li>
     </ul> </p> <p>Mer information om mätningsindikatorer finns i <i>Användarhandbok för Data Workbench</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Tillåt omgenerering av rapporter </td>
   <td colname="col2"> <p>Anger om <span class="keyword"> Rapportserver </span> genererar eller återskapar automatiskt vissa rapporter när du skapar eller ändrar dessa rapporter. Alternativen är true eller false. Om värdet är true orsakar det att en rapportarbetsyta skapas eller ändras <span class="keyword"> Rapportserver </span> för att återskapa rapporten för den senaste körningen. </p> <p> <p>Obs! Ändra <span class="filepath"> Report.cfg </span> filorsaker <span class="keyword"> Rapportserver </span> för att återskapa alla rapporter som styrs av detta <span class="filepath"> Report.cfg </span> -fil. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Bifogade filer </td>
   <td colname="col2"> <p><i>Valfritt</i>. Avsnittsidentifierare för namn och innehållstyp för bilagor som skickas med rapporter som distribueras via e-post, inklusive antalet bilagor. </p> <p>Så här lägger du till en ny bifogad fil:
     <ol id="ol_CBDC1E95D34A4D08A862680127438433">
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Öppna <span class="filepath"> Report.cfg </span> i Data Workbench. </li>
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Högerklicka <span class="uicontrol"> Bifogade filer </span> och klicka <span class="uicontrol"> Lägg till nytt underordnat objekt </span> &gt; <span class="uicontrol"> Bifogad fil </span>. </li>
     </ol> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Innehållstyp </td>
   <td colname="col2"> <p>Innehållstypen för filen som ska bifogas. </p> <p>Exempel: image/jpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> FileName </td>
   <td colname="col2"> <p>Plats och namn för filen som ska bifogas. </p> <p>Exempel: <span class="filepath"> c:\myimage.jpg </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Färguppsättning </td>
   <td colname="col2"> Identifierar det färgschema som ska användas för <span class="filepath"> .png </span> filer. 0 är för svart bakgrund, 1 är för vit bakgrund, och 2 är för en gråskalebild. </td>
  </tr>
  <tr>
   <td colname="col1"> Kommando som ska köras </td>
   <td colname="col2"> <i>Valfritt</i>. Ett gruppkommando eller en körbar fil som körs efter att rapportuppsättningen har skapats. Om kommandotolken måste startas måste du skriva cmd /c före kommandot. </td>
  </tr>
  <tr>
   <td colname="col1"> Excel-standardmall </td>
   <td colname="col2"> <p><i>Valfritt</i>. Filnamn för den generiska Excel-mallfilen ( <span class="filepath"> .xls </span> eller <span class="filepath"> .xlsx </span>) som du vill använda när du skapar rapporter som Excel-filer. Den här parametern stöder fullständiga filsökvägar, som <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>Den här filen används för alla Excel-rapporter såvida inte en mall har definierats specifikt för en viss rapport. Se <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Använda en mallfil </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Dimensionsnamn </td>
   <td colname="col2"> <i>Valfritt</i>. Namnet på dimensionen som du vill generera en rapport för dynamiskt. Om du anger ett dimensionsnamn i den här parametern måste du ange ett värde antingen i parametern Sök efter fil eller i parametrarna Övre N mått och Övre N värde. Dimensionen som namnges i den här parametern måste finnas i den datauppsättning som rapporter skapas för. </td>
  </tr>
  <tr>
   <td colname="col1"> E-post endast om perfekt </td>
   <td colname="col2"> <i>Valfritt</i>. Användaren kan ange att en rapportuppsättning bara ska skickas ut när inga fel inträffar under körningen. Alternativen är true och false. Standardvärdet är false. </td>
  </tr>
  <tr>
   <td colname="col1"> Slutdatum </td>
   <td colname="col2"> <p><i>Valfritt</i>. Det senaste datum och den senaste tidpunkt som du vill att rapportuppsättningen ska köras. Den här tiden baseras på datamängdens Från och med-tid. </p> <p>Format: MM/DD/YYY hh:mm-tidszon, med 24-timmars syntax för tid </p> <p>Exempel: 08/01/2007 12:01 EDT </p> <p>Mer information om tidszonsinställningar finns i <i>Konfigurationshandbok för datauppsättning</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Varje </td>
   <td colname="col2"> Genereringsfrekvens för rapportuppsättningen: dag, vecka eller månad. </td>
  </tr>
  <tr>
   <td colname="col1"> Timeout för Excel-övervakning (sekunder) </td>
   <td colname="col2"> <p><i>Valfritt</i>. Antalet sekunder som du vill ha <span class="keyword"> Rapportserver </span> väntar på att Microsoft Excel ska svara när en rapport genereras som en Excel-fil innan <span class="keyword"> Rapportserver </span> bestämmer att Excel inte svarar och avslutar processen. Med den här parametern aktiveras <span class="keyword"> Rapportserver </span> för att avsluta Excel när det inte svarar och fortsätta att bearbeta rapporter som inte kommer från Excel. Standardvärdet är 300.0. Om du vill inaktivera den här funktionen anger du parametern till 0,0. </p> <p>Kontrollera att det värde du anger är tillräckligt långt för att rapporten ska kunna exporteras till Excel. I annat fall <span class="keyword"> Rapportserver </span> kan avsluta Excel i förtid och rapporten genereras inte. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Filterformel </td>
   <td colname="col2"> <p><i>Valfritt</i>. Filter som används på alla arbetsytor i rapportuppsättningen. </p> <p>Mer information finns i <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> syntax för att skapa filter </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Gammakorrigering </td>
   <td colname="col2"> <p>Gammainställning för <span class="filepath"> .png </span> filutdata. Standardvärdet är 1.6. </p> <p> <p>Obs! Adobe rekommenderar att du inte ändrar det här värdet. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Göm logotyper </td>
   <td colname="col2"> Anger om Report Server döljer logotyperna när dina rapporter genereras. Alternativen är <span class="filepath"> true </span> eller <span class="filepath"> false </span>. Om inställt på <span class="filepath"> false </span>, genereras rapporten med rapportlogotypen. Standardvärdet är <span class="filepath"> false </span>. </td>
  </tr>
  <tr>
   <td colname="col1"> Sökfil </td>
   <td colname="col2"> <p><i>Valfritt</i>. När den här Dimensionen är ifylld körs Report Server i dynamiskt läge och skapar rapporter för varje element i dimensionen som anges i parametern  Name. Filen måste innehålla två tabbavgränsade kolumner, utan rubrikrad. </p> <p>
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A">
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">Kolumn 1 innehåller en lista med dimensionselement. </li>
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">Kolumn 2 innehåller rapportmottagarnas e-postadresser. En rapport för ett visst element i kolumn 1 skickas till e-postadressen på samma rad i kolumn 2. Du kan ange flera e-postadresser genom att separera dem med kommatecken (inga blanksteg). Om rapporter inte ska skickas med e-post kan den här kolumnen vara tom men måste finnas. </li>
     </ul> </p> <p> <p>Obs! Om du anger ett värde i den här Dimensionen måste du ange ett värde i parametern Namn. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Endast meddelande </td>
   <td colname="col2"> Detta <span class="wintitle"> Rapportserver </span> Med den här inställningen kan du konfigurera data workbench för att skicka ett e-postmeddelande när en rapport skapas. Värdet anges till <span class="filepath"> true </span> skickar inte rapporten, utan skickar i stället ett e-postmeddelande till den prenumererande användaren om att rapporten har genererats. </td>
  </tr>
  <tr>
   <td colname="col1"> E-postrapport </td>
   <td colname="col2"> <p>Avsnittsidentifierare för att distribuera rapporter via e-post. Om du vill distribuera rapporter via e-post fyller du i följande parametrar för <span class="wintitle"> E-postrapport </span> post. Alla rapporter i rapportuppsättningen skickas via e-post till de e-postadresser som anges i parametern Mottagare. </p> <p> <p>Obs! Report Server skickar bara ett e-postmeddelande när minst en rapport har skapats. </p> </p> <p>Om du vill aktivera e-postmeddelanden med rapporter måste du fylla i minst följande parametrar för den här posten:
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8">
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP-server </li>
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">Mottagare </li>
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">Avsändaradress </li>
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">Endast meddelande </li>
     </ul> </p> <p> <p>Obs! Information om hur du skickar ut rapporter via e-post efter att du har genererat om en rapportuppsättning finns i <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> Redigera befintliga Report.cfg-filer </a>. </p> </p> <p>Värdet Endast meddelande är tillgängligt i 5,4x- och 5,5x-versioner. </p> <p>För att en stor uppsättning mottagare ska kunna meddelas (fler än 20) rekommenderar vi att du använder e-postdistributionslistor. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Brödtext-XSL-mall </td>
   <td colname="col2"> <p><i>Valfritt</i>. Sökväg till XSL-mallfilen som ska tillämpas på <span class="filepath"> reports.xml </span> -fil. Med den här parametern kan Report Server skicka rapporter inom det distribuerade e-postmeddelandet i stället för som bilagor. Den resulterande texten används som brödtext i e-postmeddelandet. </p> <p>Se <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Rapportera exempelfiler </a> för en exempelfil. </p> <p>Mer information om XSLT (Extensible Stylesheet Language) finns i <a href="https://www.w3.org/Style/XSL/" format="http" scope="external"> Extensible Stylesheet Language Family </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Mottagare </td>
   <td colname="col2"> E-postadresser till de personer som du vill skicka rapporten till. </td>
  </tr>
  <tr>
   <td colname="col1"> Avsändaradress </td>
   <td colname="col2"> Avsändarens e-postadress. </td>
  </tr>
  <tr>
   <td colname="col1"> Avsändarens namn </td>
   <td colname="col2"> Valfritt. Avsändarens namn. </td>
  </tr>
  <tr>
   <td colname="col1"> SMTP-server </td>
   <td colname="col2"> Adress till SMTP-serverdatorn och det lösenord och användarnamn som krävs för autentisering. </td>
  </tr>
  <tr>
   <td colname="col1"> Ämne </td>
   <td colname="col2"> <i>Valfritt</i>. Ärenderad som beskriver det e-postmeddelande som ska skickas. </td>
  </tr>
  <tr>
   <td colname="col1"> Endast meddelande </td>
   <td colname="col2"> Gör att du kan konfigurera data workbench att skicka ett e-postmeddelande när en bakgrundsrapport skapas. Om du anger värdet True skickas inte rapporten, utan ett e-postmeddelande som länkar den prenumererande användaren till rapportplatsen skickas. </td>
  </tr>
  <tr>
   <td colname="col1"> Utdatarot </td>
   <td colname="col2"> <p><i>Valfritt</i>. Utdataplats för de genererade rapportuppsättningarna. Standardvärdet är <i>&lt;profile name=""&gt;</i>\Rapporterar mapp i installationskatalogen för Report Server. </p> <p>Konfigurera <span class="keyword"> Rapportserver </span> om du vill visa rapporter på en portal anger du <span class="wintitle"> Utdatarot </span> till dokumentroten för webbservern som används för portalen. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Förinläsningsfrågefilter </td>
   <td colname="col2"> <p><i>Valfritt</i>. Den här parametern gäller bara för <span class="wintitle"> Element i övre Dimensionen </span> rapporttyp. </p> <p>Namnet på det filter som du vill använda på frågan som måste köras för att bestämma de övre N-dimensionselementen innan rapporten kan genereras. Standardvärdet är <span class="wintitle"> broken_session_filter </span>. Mer information om <span class="wintitle"> Sessionsfilter - brutet </span>, se <i>Användarhandbok för Data Workbench</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <span class="wintitle"> Rapporttyper </span> </td>
   <td colname="col2"> <p>Format som du vill använda för att generera utdata. Du kan använda något eller alla av följande alternativ för att skriva ut rapportuppsättningen i flera format samtidigt:
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9">
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel skapar en Excel-arbetsbok med en visualisering per kalkylblad. Som regel gäller att du använder Excel-filer för e-postdistribution. Se <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Generera rapporter som Microsoft Excel-filer </a>. Mer information om hur du använder en mallfil finns i <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Använda en mallfil </a>. </li>
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png skapar Portable Network Graphic-filer. Som allmän regel gäller följande: <span class="filepath"> .png </span> filer som ska visas i en webbläsare (portal). </li>
      <li id="li_869DA266E6A041A5BD343537743FAC79">En miniatyrbild skapar en miniatyrbild ( <span class="filepath"> .jpg </span> fil) för arbetsytan. Standardstorleken är 240 x 180. Om du vill ändra standardstorleken redigerar du parametrarna för miniatyrbilderna X och Y. </li>
     </ul> </p> <p>Lägga till en ny rapporttyp vid redigering <span class="filepath"> Report.cfg </span> i data workbench, högerklicka <span class="uicontrol"> Rapporttyper </span>, klicka <span class="uicontrol"> Lägg till nytt underordnat objekt </span>och välj önskad rapporttyp. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Startdatum </td>
   <td colname="col2"> <p>Det första datum och den första tidpunkt som du vill att rapportuppsättningen ska köras. Den här tiden baseras på datamängdens Från och med-tid. </p> <p>Format: MM/DD/YYY hh:mm-tidszon, med 24-timmars syntax för tid. </p> <p>Mer information om tidszonsinställningar finns i <i>Konfigurationshandbok för datauppsättning</i>. </p> <p> <p>Obs! Rapporterna börjar köras när tidsstämpeln för data i profilen matchar det angivna datumet och den angivna tiden. </p> </p> <p>Exempel: </p> <p>Om startdatumet är 08/08/2006 12:00 EST körs rapporter för data med tidsstämpeln 08/08/2006 12:00 EST och senare.
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1">
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">Dagliga rapporter kommer att köras för 2006-08-08 och därefter för data med hh:mm = 12:00 EST. </li>
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">Veckorapporter kommer att köras för 2006-08-08 och därefter var sjunde dag för data med hh:mm = 12:00 EST. </li>
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">Månadsrapporter kommer att löpa för 2006-08-08 och därefter för den 8:e dagen i varje månad för data med hh:mm = 12:00 EST. </li>
     </ul> </p> <p>The <span class="wintitle"> Rapporttid </span> Måtten påverkar rapporteringsdimensionerna"Senaste N", till exempel"Senaste 7 dagarna","Gårdagen" och"För tre veckor sedan". För frågor i Report Server <span class="wintitle"> Rapporttid </span> mått ( <span class="filepath"> Rapportera tid.mått </span>) anger vilket datum och vilken tid rapporterna ska köras. Detta är från början det datum och den tid som anges i parametern Startdatum, som sedan ökas med den period som anges av parametern Varje. För frågor i data workbench <span class="wintitle"> Rapporttid </span> mätvärdet är baserat på midnatt i måttet As of ( <span class="filepath"> Per den.metrisk </span>). På grund av skillnaden i definitionerna för rapporttidsmåttet kan du få olika resultat i data workbench och om du frågar en arbetsyta som använder dimensionen Last N. <span class="keyword"> Rapportserver </span> för samma arbetsyta. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Miniatyrbild X </td>
   <td colname="col2"> <i>Valfritt</i>. Ett heltal som styr storleken (i pixlar) på X-axeln för miniatyrbilder som genereras som utdata. </td>
  </tr>
  <tr>
   <td colname="col1"> Miniatyrbild Y </td>
   <td colname="col2"> <i>Valfritt</i>. Ett heltal som styr storleken (i pixlar) på Y-axeln för miniatyrbilder som genereras som utdata. </td>
  </tr>
  <tr>
   <td colname="col1"> Övre N-mått </td>
   <td colname="col2"> <p><i>Valfritt</i>. Se beskrivningen för parametern Top N Value. </p> <p> <p>Obs! Om du anger ett värde i den här parametern måste du ange ett värde i Dimensionen Namn och parametern Övre N värde. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Övre N-värde </td>
   <td colname="col2"> <p><i>Valfritt</i>. När den här parametern fylls i, <span class="keyword"> Rapportserver </span> körs i dynamiskt läge och genererar rapporter för det högsta antalet (som anges i den här parametern) element för den Dimension som anges i parametern Namn, räknat med det mått som anges i parametern Övre N-mått. </p> <p>Exempel: Om du anger Sida i parametern Dimension Name, Sessions i parametern Top N Metric och 5 i den här parametern listas de fem översta sidorna med det högsta antalet sessioner i den genererade rapporten. </p> <p> <p>Obs! Om du anger ett värde i den här parametern måste du ange ett värde i Dimensionen Namn och parametern Övre N mått. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Använd endast lokala exempel </td>
   <td colname="col2"> <i>Valfritt</i>. Anger om du vill <span class="keyword"> Rapportserver </span> för att generera rapporter med enbart det lokala exemplet av datauppsättningen. Om du ställer in den här parametern på true kan du visa ett exempel på rapportuppsättningen (utan att placera en inläsning på en data workbench-server) för att se hur utdata ser ut utan att ta all tid som behövs för att bearbeta data fullständigt. Detta fungerar som en testfunktion. Alternativen är true eller false. Standardvärdet är false. </td>
  </tr>
  <tr>
   <td colname="col1"> Sökväg till arbetsyta </td>
   <td colname="col2"> <p><i>Valfritt</i>. Platsen för en samling arbetsytor för en given rapportuppsättning. Detta är användbart för att underhålla en enda kopia av arbetsytor som behöver genereras och distribueras på flera sätt, med <span class="filepath"> Report.cfg </span> filer för flera rapportuppsättningar. Rotkatalogen för den här sökvägen kan vara vilken profilmapp som helst. Ange inget snedstreck (\) i början av sökvägssträngen. </p> <p>Exempel: Du kan spara de gemensamma arbetsytorna för Uppsättning A och Uppsättning B i <span class="filepath"> Rapporter\Vanliga </span> och sedan definiera <span class="filepath"> Report.cfg </span> filer för två olika rapportuppsättningar, med olika genererings- och distributionsinställningar. I båda <span class="filepath"> Report.cfg </span> filer, ställer du in parametern Sökväg för arbetsytan till <i>profilnamn</i>\Reports\Common. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> XSL-utdatafil </td>
   <td colname="col2"> <i>Valfritt</i>. Sökväg till den utdatafil som skapas när <span class="wintitle"> XSL-mall </span> används i rapportindexet. </td>
  </tr>
  <tr>
   <td colname="col1"> XSL-mall </td>
   <td colname="col2"> <p><i>Valfritt</i>. Sökväg till XSL-mallfilen som ska användas i rapportindexet. Den resulterande omformningen <span class="filepath"> .xml </span> skrivs till den angivna <span class="wintitle"> XSL-utdatafil </span>. Se <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Rapportera exempelfiler </a> för en exempelfil. </p> <p> <p>Obs! Om du inte använder <span class="filepath"> .xsl </span> när du genererar rapporter distribueras alla rapporter via e-post som bilagor. </p> </p> </td>
  </tr>
 </tbody>
</table>
