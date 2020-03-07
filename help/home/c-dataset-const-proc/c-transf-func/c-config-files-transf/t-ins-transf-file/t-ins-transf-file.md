---
description: Filen data workbenchTransform.cfg innehåller de parametrar som definierar loggkällor, dataomformningar och exporterare.
solution: Analytics
title: Filen Transform.cfg
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Filen Transform.cfg{#the-transform-cfg-file}

Filen data workbenchTransform.cfg innehåller de parametrar som definierar loggkällor, dataomformningar och exporterare.

De omformningar som du definierar hanterar rådata som samlats in av sensorer ( [!DNL .vsl] filer) eller som finns i textfiler, XML-filer eller ODBC-kompatibla databaser och skriver ut dem antingen i befintliga fält, skriver över aktuella data eller i nya fält.

Om du vill konfigurera omformningsfunktioner redigerar du data workbench- [!DNL Transform.cfg] filen i datauppsättningsmappen för den profil som du vill exportera händelsedata för. Den här profilen är vanligtvis dedikerad till omformningsfunktioner (det vill säga du utför ingen annan databearbetning än vad som definieras i data workbench- [!DNL Transform.cfg] filen). Det är viktigt att notera att eventuella bearbetningsinstruktioner som anges i filerna för alla ärvda profiler tillämpas utöver de som anges i data workbench- [!DNL Log Processing Dataset Include] [!DNL Transform.cfg] filen.

Mer information om datauppsättningsfiler finns i [Inkludera datauppsättningar](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Om de data som du vill exportera bearbetas av ett Data Workbench-serverkluster, bearbetar varje DPU i klustret data, men bara den första DPU (bearbetningsserver #0 i [!DNL profile.cfg] filen) skriver utdata till det lokala filsystemet.

**Redigera filen Transform.cfg för data workbench**

1. När du arbetar i den profil som du vill exportera data för öppnar du [!DNL Profile Manager] och klickar på **[!UICONTROL Dataset]** för att visa innehållet i katalogen.
1. Högerklicka på bockmarkeringen bredvid data workbench [!DNL Transform.cfg]och klicka sedan på **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Data Workbench- [!DNL Transform.cfg] fönstret visas.
1. Redigera parametrarna i konfigurationsfilen med hjälp av tabellen nedan som vägledning:

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
  <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parameter </th> 
    <th colname="col2" class="entry"> Beskrivning </th> 
    </tr> 
  </thead>
  <tbody> 
    <tr> 
    <td colname="col1"> Sluttid </td> 
    <td colname="col2"> <p>Valfritt. Filtrera data för att inkludera loggposter med tidsstämplar fram till, men inte inklusive, den här gången. Adobe rekommenderar att du använder något av följande format för tillfället: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1 januari 2013HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1 januari 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Om du till exempel anger 29 juli 2013 00:00:00 EDT som <span class="wintitle"> sluttid </span> inkluderas data till och med 28 juli 2013, kl. 11:59:59 EDT. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench-servern finns i <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> Parametern Använd start-/sluttider för sensorns och loggfilens källor är relaterad till den här parametern. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exportörer </td> 
    <td colname="col2"> <p>En exportörs underfält anger hur utdata bearbetas och/eller formateras. Du kan definiera flera exporterare för en uppsättning loggkällor. Varje exporttyp skapar utdata oberoende av varandra. </p> <p> Det finns tre typer av exportörer: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Mer information om exporterartyper finns i <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definiera exporterare </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hash-tröskelvärde </td> 
    <td colname="col2"> Valfritt. En samplingsfaktor för slumpmässig delsampling av rader. Om värdet är ett tal n markeras endast ett av varje n spårnings-ID för export, vilket minskar det totala antalet rader som exporteras med faktorn n. Om du vill exportera alla rader ställer du in Hash-tröskelvärdet till 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Loggpostvillkor </td> 
    <td colname="col2"> Valfritt. Definierar reglerna som loggposter ska exporteras med. Mer information om villkoren för <span class="wintitle"> loggpost </span>finns i <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Loggbehandlingens konfigurationsfil </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Loggkällor </td> 
    <td colname="col2"> <p>Datakällor. <span class="wintitle"> Loggkällor </span> kan vara <span class="filepath"> .vsl- </span> filer, loggfiler, XML-filer eller data från ODBC-kompatibla databaser. Mer information om <span class="wintitle"> loggkällor </span>finns i <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Loggbehandlingens konfigurationsfil </a>. </p> <p> <span class="wintitle"> Transform </span> förväntar att alla källdata ska vara i kronologisk ordning inom lexikografiskt ordnade indatafiler. Om det här kravet inte uppfylls, blir beräkningen från och med felaktig och ytterligare indata kan bearbetas efter att utdatafilerna har stängts. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offlineläge </td> 
    <td colname="col2"> <p>Valfritt. Sant eller falskt. Om värdet är true <span class="wintitle"> </span> antar Transform att alla indatafiler finns när databearbetningen startar. När alla indata har lästs <span class="wintitle"> </span> stänger Transform alla utdatafiler utan att vänta på att ytterligare data ska tas emot. Standardvärdet är false. </p> <p> <p>Obs!  Om <span class="wintitle"> offlineläget </span> är true, kommer alla källdata att finnas <span class="wintitle"> </span> innan bearbetningen startar. Ett varningsmeddelande genereras i <span class="filepath"> VisualServer.log- </span> filen om ytterligare data tas emot efter att utdatafilerna har stängts. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Återbearbeta </td> 
    <td colname="col2"> <p>Valfritt. Här kan du ange alla tecken eller teckenkombinationer. Om du ändrar den här parametern och sparar filen på <span class="wintitle"> Transform- </span> datorn initieras databearbetningen. </p> <p> Mer information om hur du ombearbetar data finns i <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Återbearbetning och omformning </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Steg </td> 
    <td colname="col2"> <p>Valfritt. Namnen på de bearbetningsfaser som kan användas i <span class="wintitle"> Loggbearbetning av datauppsättning omfattar </span> filer som körs utöver data workbench- <span class="filepath"> Transform.cfg- </span> filen. Bearbetningsfaserna är ett sätt att ordna de omformningar som definieras i <span class="wintitle"> Loggbearbetning av datauppsättning Inkludera </span> filer. Den här parametern är mycket användbar om du har definierat en eller flera omformningar i flera <span class="wintitle"> loggbehandlingsdatauppsättningar Inkludera </span> filer och du vill att specifika omformningar ska utföras vid specifika punkter under exportprocessen. </p> <p> Den ordning i vilken du listar stegen här avgör i vilken ordning omformningarna i <span class="wintitle"> loggdatauppsättningen Inkludera </span> filer utförs vid dataexport. <span class="wintitle"> Förbehandling </span> och <span class="wintitle"> efterbehandling </span> är inbyggda. <span class="wintitle"> Förbehandling </span> är alltid det första steget och <span class="wintitle"> Efterbearbetning </span> är alltid det sista steget. Som standard finns det en scen med namnet <span class="wintitle"> Default </span>. </p> <p> <b>Lägga till en ny bearbetningsfas</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> I Data Workbench <span class="filepath"> Transform.cfg- </span> fönstret högerklickar du på <span class="uicontrol"> Steg </span>och klickar sedan på <span class="uicontrol"> Lägg till ny </span> &gt; <span class="uicontrol"> Scen </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Ange ett namn för den nya scenen. </li> 
      </ul> <p> <b>Ta bort en befintlig bearbetningsfas</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Högerklicka på numret för den scen som du vill ta bort och klicka på <span class="uicontrol"> Ta bort </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Obs!  När du anger en scen i en <span class="wintitle"> loggbearbetningsdatauppsättning med inkluderingsfil måste scenens namn </span> matcha exakt det namn du anger här. Mer information om datauppsättningsfiler finns i <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Inkludera datauppsättningar </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Starttid </td> 
    <td colname="col2"> <p>Valfritt. Filtrera data för att inkludera loggposter med tidsstämplar vid eller efter den här tidpunkten. Adobe rekommenderar att du använder något av följande format för tillfället: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1 januari 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1 januari 2013 HH:MM:SS GMT </li> 
      </ul> <p> Om du till exempel anger 29 juli 2013 00:00:00 EDT som starttid inkluderas data från och med 29 juli 2013, kl. 12:00:00 EDT. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench-servern finns i <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> <p>Obs!  Parametern Använd start-/sluttider för sensorns och loggfilens källor är relaterad till den här parametern. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Omformningar </td> 
    <td colname="col2"> <p>Valfritt. Definierar de omformningar som ska tillämpas på data. Mer information om tillgängliga omformningstyper finns i <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datatransformeringar </a>. </p> <p> <p>Obs!  Följande omformningstyper fungerar inte när de definieras i <span class="filepath"> Transform.cfg- </span> filen för Data Workbench: </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> Korsrader </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Skändis </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Om ytterligare data tas emot efter att utdatafilerna har stängts (se [!DNL Log Sources] och [!DNL Offline Mode] i föregående tabell) [!DNL Transform] skapar nya utdatafiler med ytterligare data. Namnen på de nya utdatafilerna genereras från den ursprungliga utdatafilens namn med tillägget parenteserat versionsnummer precis före tillägget. Om den ursprungliga utdatafilen till exempel är [!DNL 20070701-ABC.vsl], kommer efterföljande versioner av den här filen att namnges [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]och så vidare. Observera att om du använder versionshanteringsfiler som indata till data workbench-servern kan det leda till bearbetningsfel.
>
>
>Adobe rekommenderar att du undviker att skapa versionshanterade utdatafiler genom att se till att alla källdata är i kronologisk ordning i lexikografiskt ordnade indatafiler och, om [!DNL Offline Mode] värdet är true, att alla källdata finns innan bearbetningen startar. Mer information finns i avsnitten [!DNL Log Sources] och [!DNL Offline Mode] i föregående tabell.

1. Lägg till omformningar genom att högerklicka **[!UICONTROL Transformations]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Fyll i omformningsfälten.

   Se [Dataomvandlingar](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) för beskrivningar och exempel på omvandlingar som du kan använda med omformningsfunktioner.

1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.
1. Om du vill göra de lokalt gjorda ändringarna gällande [!DNL Profile Manager]högerklickar du på bockmarkeringen för data workbench [!DNL Transform.cfg] i [!DNL User] kolumnen och klickar sedan **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, där profilnamnet är namnet på den profil som du exporterar data för. Ombearbetningen av data börjar efter synkronisering av profilen.

   >[!NOTE]
   >
   >Mer information om hur du ombearbetar data för export finns i [Återbearbetning och omformning](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
