---
description: Steg för att redigera Transformation.cfg-filen för en datauppsättningsprofil.
title: Redigera transformeringskonfigurationsfilen
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
exl-id: 3fab17a4-d356-4548-b977-f5d409870753
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 0%

---

# Redigera transformeringskonfigurationsfilen{#editing-the-transformation-configuration-file}

{{eol}}

Steg för att redigera Transformation.cfg-filen för en datauppsättningsprofil.

1. Öppna dialogrutan [!DNL Profile Manager] och klicka **[!UICONTROL Dataset]** för att visa innehållet.

   Mer information om hur du öppnar och arbetar med [!DNL Profile Manager], se *Användarhandbok för Data Workbench*.

   >[!NOTE]
   >
   >Det kan finnas en Transformation-underkatalog i datauppsättningskatalogen. Den här underkatalogen innehåller [!DNL Transformation Dataset Include] filer som har skapats för en eller flera ärvda profiler. Mer information om [!DNL Transformation Dataset Include] filer, se [Datauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Högerklicka på bockmarkeringen bredvid [!DNL Transformation.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. The [!DNL Transformation.cfg] visas.

   Du kan även öppna [!DNL Transformation.cfg] från en [!DNL Transformation Dependency Map]. Mer information om [!DNL transformation dependency maps], se [Verktyg för datauppsättningskonfiguration](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Redigera parametrarna i konfigurationsfilen med följande tabell som hjälp.

   När du redigerar [!DNL Transformation.cfg] i ett datas workbench-fönster kan du använda kortkommandon för grundläggande redigeringsfunktioner, t.ex. klipp ut (Ctrl+X), kopiera (Ctrl+C), klistra in (Ctrl+V), ångra (Ctrl+Z), göra om (Ctrl+Skift+Z), markera avsnitt (klicka+dra) och markera alla (Ctrl+a). Du kan dessutom använda kortkommandona för att kopiera och klistra in text från en konfigurationsfil ( [!DNL .cfg]) till en annan.

   >[!NOTE]
   >
   >A [!DNL Transformation Dataset Include] filer för en ärvd profil innehåller en delmängd av parametrarna som beskrivs i följande tabell samt ytterligare parametrar. Mer information om [!DNL Transformation Dataset Include] filer, se [Datauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
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
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1 januari 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1 januari 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Ange till exempel"29 juli 2013 00:00:00 EDT" som sluttid innehåller data fram till 28 juli 2013, 11:59:59 PM EDT. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench-servern finns på <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> <p>Obs! Om du anger ett värde för Sluttid anges parametern Sluttid och används under datauppsättningens omformningsfas. Mer information om parametrar finns i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definiera parametrar i datauppsättningen inkluderar filer </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Utökade Dimensioner </td> 
      <td colname="col2"> Valfritt. Adobe rekommenderar att du definierar utökade dimensioner i en eller flera <span class="wintitle"> Omformningsdatauppsättningen innehåller </span> filer. Mer information finns i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Omvandlingsdatauppsättningen innehåller filer </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash-tröskelvärde </td> 
      <td colname="col2"> <p>Valfritt. En samplingsfaktor för slumpmässig delsampling av rader. Om värdet är ett tal n kommer endast ett av varje n spårnings-ID att matas in i datauppsättningen, vilket minskar det totala antalet rader i datauppsättningen med faktorn n. Om du vill skapa en datauppsättning som kräver 100 procents noggrannhet (d.v.s. att alla rader tas med) anger du ett hash-tröskelvärde. </p> <p> Om hash-tröskelvärdet anges i båda <span class="filepath"> Loggbearbetning.cfg </span> och <span class="filepath"> Transformation.cfg </span> filer, som inte tillämpas i sekvens, det högsta värdet som anges i någon av konfigurationsfilerna gäller. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Loggpostvillkor </td> 
      <td colname="col2"> Valfritt. Definierar reglerna som loggposter som genereras från loggbearbetning ska tas med i datauppsättningsprofilen. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Loggpostvillkor </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nytt besökarvillkor </td> 
      <td colname="col2"> Valfritt. För användning med webbdata. Definierar de regler som besökare ska övervägas att ta med i data. The <span class="wintitle"> Nytt besökarvillkor </span> definierar den första loggposten för en besökare (ordnade efter tid) som ska användas i datauppsättningen. Alla efterföljande loggposter för den här besökaren inkluderas i datauppsättningen oavsett om de uppfyller det här villkoret eller inte. Se <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Nytt besökarvillkor </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Återbearbeta </td> 
      <td colname="col2"> <p>Valfritt. Här kan du ange alla tecken eller teckenkombinationer. Om du ändrar den här parametern och sparar filen initieras omformningen av data. </p> <p> Mer information om hur du bearbetar dina data finns i <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Ombearbetning och omformning </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schemakontroll </td> 
      <td colname="col2"> Sant eller falskt. Om värdet är true identifierar data workbench-servern skadade datauppsättningar och registrerar information om problemen i loggfiler i data workbench-serverns Trace-katalog. Standardvärdet är true. Adobe rekommenderar att du alltid låter den här parametern vara inställd på true. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Steg </td> 
      <td colname="col2"> <p>Valfritt. Namnen på de bearbetningsfaser som kan användas i <span class="wintitle"> Omformningsdatauppsättningen innehåller </span> filer. Bearbetningsfaserna är ett sätt att ordna omformningarna som definieras i <span class="wintitle"> Omformningsdatauppsättningen innehåller </span> filer. Den här parametern är mycket användbar om du har definierat en eller flera omformningar i flera <span class="wintitle"> Omformningsdatauppsättningen innehåller </span> och du vill att specifika omformningar ska utföras vid specifika punkter under omformningen. </p> <p> Den ordning i vilken du listar stadierna här avgör i vilken ordning omformningarna i <span class="wintitle"> Omformningsdatauppsättningen innehåller </span> filer körs under omformningen. <span class="wintitle"> Förbehandling </span> och <span class="wintitle"> Efterbehandling </span> är inbyggda, <span class="wintitle"> Förbehandling </span> är alltid det första steget, och <span class="wintitle"> Efterbehandling </span> är alltid sista steget. Som standard finns det en namngiven scen som kallas <span class="wintitle"> Standard </span>. </p> <p> <b>Lägga till en ny bearbetningsfas</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> I <span class="filepath"> Transformation.cfg </span> fönster, högerklicka <span class="uicontrol"> Steg </span> och klicka <span class="uicontrol"> Lägg till ny </span> &gt; <span class="uicontrol"> Scen </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Ange ett namn för den nya scenen. </li> 
      </ul> </p> <p> <b>Ta bort en befintlig bearbetningsfas</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Högerklicka på numret för den scen som du vill ta bort och klicka på <span class="uicontrol"> Ta bort </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Obs! När du anger en scen i en <span class="wintitle"> Omformningsdatauppsättningen innehåller </span> filer måste scenens namn matcha exakt det namn du anger här. Mer information om datauppsättningsinkluderingsfiler finns i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datauppsättningen innehåller filer </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Starttid </td> 
      <td colname="col2"> <p>Valfritt. Filtrera data för att inkludera loggposter med tidsstämplar vid eller efter den här tidpunkten. Adobe rekommenderar att du använder något av följande format för tillfället: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1 januari 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1 januari 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Du kan till exempel ange 29 juli 2013 00:00:00 EDT som <span class="wintitle"> Starttid </span> innehåller data från och med den 29 juli 2013, kl. 12:00:00:00 EDT. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench Server finns på <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> <p>Obs! Om du anger ett värde för Starttid anges en parameter med namnet Starttid som används under datauppsättningens omformningsfas. Mer information om parametrar finns i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definiera parametrar i datauppsättningen inkluderar filer </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Omformningar </td> 
      <td colname="col2"> Valfritt. Adobe rekommenderar att du definierar omformningar för omformningsfasen för datauppsättningskonstruktionen i en eller flera <span class="wintitle"> Omformningsdatauppsättningen innehåller </span> filer. Mer information finns i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Omvandlingsdatauppsättningen innehåller filer </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Tidszon </td> 
      <td colname="col2"> <p>Tidszon för datauppsättningsprofilen. Tidszoner används för tidskonverteringar och för att skapa tidsdimensioner. Se <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Tidszoner </a>. </p> <p> <p>Obs! Vid definition i <span class="filepath"> Loggbearbetning.cfg </span> -filen används parametern Tidszon endast för tidskonverteringar. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. I [!DNL Profile Manager], högerklicka på bockmarkeringen för [!DNL Transformation.cfg]i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** för att göra de lokala ändringarna gällande. Omformningen av data börjar efter synkronisering av datauppsättningsprofilen.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

   Mer information om hur du ombearbetar eller omformar data finns i [Ombearbetning och omformning](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
