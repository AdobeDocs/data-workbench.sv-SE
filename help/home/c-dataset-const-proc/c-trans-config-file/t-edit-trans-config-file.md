---
description: Steg för att redigera Transformation.cfg-filen för en datauppsättningsprofil.
solution: Analytics
title: Redigera transformeringskonfigurationsfilen
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Redigera transformeringskonfigurationsfilen{#editing-the-transformation-configuration-file}

Steg för att redigera Transformation.cfg-filen för en datauppsättningsprofil.

1. När du arbetar i datauppsättningsprofilen öppnar du filen [!DNL Profile Manager] och klickar **[!UICONTROL Dataset]** för att visa dess innehåll.

   Mer information om hur du öppnar och arbetar med [!DNL Profile Manager]filen finns i *användarhandboken* för Data Workbench.

   >[!NOTE]
   >
   >Det kan finnas en Transformation-underkatalog i datauppsättningskatalogen. Den här underkatalogen innehåller de filer [!DNL Transformation Dataset Include] som har skapats för en eller flera ärvda profiler. Mer information om [!DNL Transformation Dataset Include] filer finns i [Inkludera filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)i datauppsättning.

1. Högerklicka på bockmarkeringen bredvid [!DNL Transformation.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Fönstret [!DNL Transformation.cfg] visas.

   Du kan också öppna filen från en [!DNL Transformation.cfg] PDF-fil [!DNL Transformation Dependency Map]. Mer information om [!DNL transformation dependency maps]finns i [Verktyg](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)för datauppsättningskonfiguration.

1. Redigera parametrarna i konfigurationsfilen med följande tabell som hjälp.

   När du redigerar [!DNL Transformation.cfg] filen i ett datarubrikfönster kan du använda kortkommandon för grundläggande redigeringsfunktioner, till exempel klipp ut (Ctrl+x ), kopiera (Ctrl+C), klistra in (Ctrl+V), ångra (Ctrl+z ), göra om (Ctrl+Skift+z ), markera avsnitt (klicka+dra) och markera alla (Ctrl+a). Du kan dessutom använda kortkommandona för att kopiera och klistra in text från en konfigurationsfil ( [!DNL .cfg]) till en annan.

   >[!NOTE]
   >
   >En [!DNL Transformation Dataset Include] fil för en ärvd profil innehåller en delmängd av parametrarna som beskrivs i följande tabell samt några ytterligare parametrar. Mer information om [!DNL Transformation Dataset Include] filer finns i [Inkludera filer i datauppsättning](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

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
      </ul> </p> <p> Om du till exempel anger"29 juli 2013 00:00:00 EDT" som sluttid inkluderas data fram till 28 juli 2013, kl. 11:59:59 EDT. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench-servern finns i <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> <p>Obs!  Om du anger ett värde för Sluttid anges parametern Sluttid och används under datauppsättningens omformningsfas. Mer information om parametrar finns i Definiera parametrar i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Inkludera filer i datauppsättningen </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Utökade dimensioner </td> 
      <td colname="col2"> Valfritt. Adobe rekommenderar att du definierar utökade dimensioner i en eller flera <span class="wintitle"> Transformation Dataset Include- </span> filer. Mer information finns i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Inkludera filer i datauppsättningen för omvandling </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash-tröskelvärde </td> 
      <td colname="col2"> <p>Valfritt. En samplingsfaktor för slumpmässig delsampling av rader. Om värdet är ett tal n kommer endast ett av varje n spårnings-ID att matas in i datauppsättningen, vilket minskar det totala antalet rader i datauppsättningen med faktorn n. Om du vill skapa en datauppsättning som kräver 100 procents noggrannhet (d.v.s. att alla rader tas med) anger du ett hash-tröskelvärde. </p> <p> Om hash-tröskelvärdet anges både i <span class="filepath"> loggfilerna </span> Log Processing.cfg <span class="filepath"> och </span> Transformation.cfg tillämpas det inte i sekvens. det högsta värdet som anges i någon av konfigurationsfilerna gäller. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Loggpostvillkor </td> 
      <td colname="col2"> Valfritt. Definierar reglerna som loggposter som genereras från loggbearbetning ska tas med i datauppsättningsprofilen. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Loggpostvillkor </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nytt besökarvillkor </td> 
      <td colname="col2"> Valfritt. För användning med webbdata. Definierar de regler som besökare ska övervägas att ta med i data. Det nya <span class="wintitle"> besökarvillkoret </span> definierar den första loggposten för en besökare (ordnade efter tid) som ska användas i datauppsättningen. Alla efterföljande loggposter för den här besökaren inkluderas i datauppsättningen oavsett om de uppfyller det här villkoret eller inte. Se <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Nytt besökarvillkor </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Återbearbeta </td> 
      <td colname="col2"> <p>Valfritt. Här kan du ange alla tecken eller teckenkombinationer. Om du ändrar den här parametern och sparar filen initieras omformningen av data. </p> <p> Mer information om hur du ombearbetar data finns i <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Återbearbetning och omformning </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schemakontroll </td> 
      <td colname="col2"> Sant eller falskt. Om värdet är true identifierar data workbench-servern skadade datauppsättningar och registrerar information om problemen i loggfiler i data workbench-serverns Trace-katalog. Standardvärdet är true. Adobe rekommenderar att du alltid låter den här parametern vara true. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Steg </td> 
      <td colname="col2"> <p>Valfritt. Namnen på de bearbetningsfaser som kan användas i <span class="wintitle"> Transformation Dataset innehåller </span> filer. Bearbetningsfaserna är ett sätt att ordna omformningarna som definieras i <span class="wintitle"> Omvandlingsdatauppsättningen Inkludera </span> filer. Den här parametern är mycket användbar om du har definierat en eller flera omformningar i flera <span class="wintitle"> omformningsdatauppsättningar, inklusive </span> filer, och du vill att specifika omformningar ska utföras vid specifika punkter under omformningen. </p> <p> Den ordning i vilken du listar stegen här avgör i vilken ordning omformningarna i <span class="wintitle"> Omvandlingsdatauppsättningen Inkludera </span> filer utförs under omformningen. <span class="wintitle"> Förbehandling </span> och <span class="wintitle"> efterbehandling </span> är inbyggda. <span class="wintitle"> Förbehandling </span> är alltid det första steget och <span class="wintitle"> Efterbearbetning </span> är alltid det sista steget. Som standard finns det en scen med namnet <span class="wintitle"> Default </span>. </p> <p> <b>Lägga till en ny bearbetningsfas</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> I <span class="filepath"> fönstret </span> Transformation.cfg högerklickar du på <span class="uicontrol"> Stages </span> och klickar på <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Ange ett namn för den nya scenen. </li> 
      </ul> </p> <p> <b>Ta bort en befintlig bearbetningsfas</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Högerklicka på numret för den scen som du vill ta bort och klicka på <span class="uicontrol"> Ta bort </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Obs!  När du anger en scen i en <span class="wintitle"> Transformation Dataset Include- </span> filer måste scenens namn matcha exakt det namn du anger här. Mer information om datauppsättningsfiler finns i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Inkludera datauppsättningar </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Starttid </td> 
      <td colname="col2"> <p>Valfritt. Filtrera data för att inkludera loggposter med tidsstämplar vid eller efter den här tidpunkten. Adobe rekommenderar att du använder något av följande format för tillfället: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1 januari 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1 januari 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Om du till exempel anger 29 juli 2013 00:00:00 EDT som <span class="wintitle"> starttid </span> inkluderas data från och med 29 juli 2013, kl. 12:00:00 EDT. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench Server finns i <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> <p>Obs!  Om du anger ett värde för Starttid anges en parameter med namnet Starttid som används under datauppsättningens omformningsfas. Mer information om parametrar finns i Definiera parametrar i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Inkludera filer i datauppsättningen </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Omformningar </td> 
      <td colname="col2"> Valfritt. Adobe rekommenderar att du definierar omformningar för omformningsfasen för datauppsättningens konstruktion i en eller flera <span class="wintitle"> Transformation DataSet Include- </span> filer. Mer information finns i <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Inkludera filer i datauppsättningen för omvandling </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Tidszon </td> 
      <td colname="col2"> <p>Tidszon för datauppsättningsprofilen. Tidszoner används för tidskonverteringar och för att skapa tidsdimensioner. Se <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Tidszoner </a>. </p> <p> <p>Obs!  När den definieras i <span class="filepath"> filen </span> Log Processing.cfg används parametern Time Zone endast för tidskonverteringar. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.
1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen för [!DNL Transformation.cfg]i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** för att ändringarna ska börja gälla lokalt. Omformningen av data börjar efter synkronisering av datauppsättningsprofilen.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profiler som tillhandahålls av Adobe, eftersom dina ändringar skrivs över när du installerar uppdateringar för dessa profiler.

   Mer information om ombearbetning eller omformning av data finns i [Återbearbetning och omformning](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
