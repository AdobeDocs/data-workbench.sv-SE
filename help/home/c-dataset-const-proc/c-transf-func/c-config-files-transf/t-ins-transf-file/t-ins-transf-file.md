---
description: Filen data workbenchTransform.cfg innehåller de parametrar som definierar loggkällor, dataomformningar och exporterare.
title: Filen Transform.cfg
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 0%

---

# Filen Transform.cfg{#the-transform-cfg-file}

{{eol}}

Filen data workbenchTransform.cfg innehåller de parametrar som definierar loggkällor, dataomformningar och exporterare.

De omformningar som du definierar hanterar rådata som samlats in av sensorer ( [!DNL .vsl] filer) eller som finns i textfiler, XML-filer eller ODBC-kompatibla databaser och som kan skrivas ut i befintliga fält, skrivas över aktuella data eller i nya fält.

Om du vill konfigurera omformningsfunktioner redigerar du data workbench [!DNL Transform.cfg] i mappen Dataset för den profil som du vill exportera händelsedata för. Den här profilen är vanligtvis dedikerad till omvandlingsfunktioner (det vill säga du utför ingen annan databearbetning än vad som är definierat i data workbench) [!DNL Transform.cfg] fil). Det är viktigt att notera att eventuella bearbetningsinstruktioner som anges i [!DNL Log Processing Dataset Include] filer för alla ärvda profiler används utöver de som anges i data workbench [!DNL Transform.cfg] -fil.

Mer information om datauppsättningens inkluderingsfiler finns i [Datauppsättningen innehåller filer](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Om de data som du vill exportera bearbetas av ett Data Workbench-serverkluster, bearbetar varje DPU i klustret data, men bara den första DPU (bearbetningsservern #0 i [!DNL profile.cfg] -filen) skriver utdata till det lokala filsystemet.

**Redigera filen Transform.cfg för data workbench**

1. Öppna dialogrutan [!DNL Profile Manager] och klicka **[!UICONTROL Dataset]** för att visa innehållet i katalogen.
1. Högerklicka på bockmarkeringen bredvid data workbench [!DNL Transform.cfg]och sedan klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Data Workbench [!DNL Transform.cfg] visas.
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
      </ul> </p> <p> Du kan till exempel ange 29 juli 2013 00:00:00 EDT som <span class="wintitle"> Sluttid </span> innehåller data fram till 28 juli 2013, 11:59:59 PM EDT. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench-servern finns på <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> Parametern Använd start-/sluttider för sensorns och loggfilens källor är relaterad till den här parametern. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exportörer </td> 
    <td colname="col2"> <p>En exportörs underfält anger hur utdata bearbetas och/eller formateras. Du kan definiera flera exporterare för en uppsättning loggkällor. Varje exporttyp skapar utdata oberoende av varandra. </p> <p> Det finns tre typer av exportörer: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Mer information om exportörstyper finns i <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Definiera exporterare </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hash-tröskelvärde </td> 
    <td colname="col2"> Valfritt. En samplingsfaktor för slumpmässig delsampling av rader. Om värdet är ett tal n markeras endast ett av varje n spårnings-ID för export, vilket minskar det totala antalet rader som exporteras med faktorn n. Om du vill exportera alla rader ställer du in Hash-tröskelvärdet till 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Loggpostvillkor </td> 
    <td colname="col2"> Valfritt. Definierar reglerna som loggposter ska exporteras med. Mer information om <span class="wintitle"> Loggpostvillkor </span>, se <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsfil för loggbearbetning </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Loggkällor </td> 
    <td colname="col2"> <p>Datakällor. <span class="wintitle"> Loggkällor </span> kan <span class="filepath"> .vsl </span> filer, loggfiler, XML-filer eller data från ODBC-kompatibla databaser. Mer information om <span class="wintitle"> loggkällor </span>, se <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Konfigurationsfil för loggbearbetning </a>. </p> <p> <span class="wintitle"> Omforma </span> Alla källdata förväntas vara i kronologisk ordning inom lexikografiskt ordnade indatafiler. Om det här kravet inte uppfylls, blir beräkningen från och med felaktig och ytterligare indata kan bearbetas efter att utdatafilerna har stängts. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offlineläge </td> 
    <td colname="col2"> <p>Valfritt. Sant eller falskt. Om true, <span class="wintitle"> Omforma </span> förutsätter att alla indatafiler finns när databearbetningen börjar. När alla indata har lästs <span class="wintitle"> Omforma </span> stänger alla utdatafiler utan att vänta på att ytterligare data ska tas emot. Standardvärdet är false. </p> <p> <p>Obs! If <span class="wintitle"> Offlineläge </span> är inställt på true, <span class="wintitle"> Omforma </span> Alla källdata förväntas finnas innan bearbetningen startar. Ett varningsmeddelande genereras i <span class="filepath"> VisualServer.log </span> om ytterligare data tas emot efter att utdatafilerna har stängts. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Återbearbeta </td> 
    <td colname="col2"> <p>Valfritt. Här kan du ange alla tecken eller teckenkombinationer. Ändra den här parametern och spara filen i <span class="wintitle"> Omforma </span> datorn initierar dataombearbetning. </p> <p> Mer information om hur du bearbetar dina data finns i <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Ombearbetning och omformning </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Steg </td> 
    <td colname="col2"> <p>Valfritt. Namnen på de bearbetningsfaser som kan användas i <span class="wintitle"> Loggbehandlingens datauppsättning innehåller </span> filer som körs utöver data workbench <span class="filepath"> Transform.cfg </span> -fil. Bearbetningsfaserna är ett sätt att ordna omformningarna som definieras i <span class="wintitle"> Loggbehandlingens datauppsättning innehåller </span> filer. Den här parametern är mycket användbar om du har definierat en eller flera omformningar i flera <span class="wintitle"> Loggbehandlingens datauppsättning innehåller </span> och du vill att specifika omformningar ska utföras vid specifika punkter under exportprocessen. </p> <p> Den ordning i vilken du listar stadierna här avgör i vilken ordning omformningarna i <span class="wintitle"> Loggbehandlingens datauppsättning innehåller </span> filer körs under dataexport. <span class="wintitle"> Förbehandling </span> och <span class="wintitle"> Efterbehandling </span> är inbyggda, <span class="wintitle"> Förbehandling </span> är alltid det första steget, och <span class="wintitle"> Efterbehandling </span> är alltid sista steget. Som standard finns det en namngiven scen som kallas <span class="wintitle"> Standard </span>. </p> <p> <b>Lägga till en ny bearbetningsfas</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> I data workbench <span class="filepath"> Transform.cfg </span> fönster, högerklicka <span class="uicontrol"> Steg </span>och sedan klicka <span class="uicontrol"> Lägg till ny </span> &gt; <span class="uicontrol"> Scen </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Ange ett namn för den nya scenen. </li> 
      </ul> <p> <b>Ta bort en befintlig bearbetningsfas</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Högerklicka på numret för den scen som du vill ta bort och klicka på <span class="uicontrol"> Ta bort </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Obs! När du anger en scen i en <span class="wintitle"> Loggbehandlingens datauppsättning innehåller </span> filen måste namnet på scenen matcha exakt det namn du anger här. Mer information om datauppsättningsinkluderingsfiler finns i <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datauppsättningen innehåller filer </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Starttid </td> 
    <td colname="col2"> <p>Valfritt. Filtrera data för att inkludera loggposter med tidsstämplar vid eller efter den här tidpunkten. Adobe rekommenderar att du använder något av följande format för tillfället: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1 januari 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1 januari 2013 HH:MM:SS GMT </li> 
      </ul> <p> Du kan till exempel ange 29 juli 2013 00:00:00 EDT som starttid innehåller data från 29 juli 2013, 12:00:00:00 EDT. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench-servern finns på <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> <p>Obs! Parametern Använd start-/sluttider för sensorns och loggfilens källor är relaterad till den här parametern. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Omformningar </td> 
    <td colname="col2"> <p>Valfritt. Definierar de omformningar som ska tillämpas på data. Mer information om tillgängliga omformningstyper finns i <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Dataomvandlingar </a>. </p> <p> <p>Obs! Följande omformningstyper fungerar inte när de definieras i data workbench <span class="filepath"> Transform.cfg </span> fil: </p> </p> 
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
>Om ytterligare data tas emot efter att utdatafilerna har stängts (se [!DNL Log Sources] och [!DNL Offline Mode] i föregående tabell), [!DNL Transform] skapar nya utdatafiler med ytterligare data. Namnen på de nya utdatafilerna genereras från den ursprungliga utdatafilens namn med tillägget parenteserat versionsnummer precis före tillägget. Om den ursprungliga utdatafilen till exempel är [!DNL 20070701-ABC.vsl]kommer efterföljande versioner av den här filen att namnges [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]och så vidare. Observera att om du använder versionshanteringsfiler som indata till data workbench-servern kan det leda till bearbetningsfel.
>
>
>Adobe rekommenderar att man undviker att skapa versionshanterade utdatafiler genom att se till att alla källdata är i kronologisk ordning i lexikografiskt ordnade indatafiler och, om [!DNL Offline Mode] är inställt på true, att alla källdata finns innan bearbetningen startar. Mer information finns i [!DNL Log Sources] och [!DNL Offline Mode] poster i föregående tabell.

1. Lägga till omformningar genom att högerklicka **[!UICONTROL Transformations]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Fyll i omformningsfälten.

   Se [Dataomvandlingar](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) för beskrivningar och exempel på omformningar som du kan använda med omformningsfunktioner.

1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka sedan på **[!UICONTROL Save]**.
1. Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklicka på bockmarkeringen för data workbench [!DNL Transform.cfg] i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, där profilnamnet är namnet på den profil som du exporterar data för. Ombearbetningen av data börjar efter synkronisering av profilen.

   >[!NOTE]
   >
   >Mer information om hur du ombearbetar data för export finns i [Ombearbetning och omformning](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
