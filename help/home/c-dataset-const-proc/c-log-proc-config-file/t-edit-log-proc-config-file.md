---
description: Steg för att redigera filen Log Processing.cfg för en datauppsättningsprofil.
title: Redigera konfigurationsfilen för loggbearbetning
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 0%

---

# Redigera konfigurationsfilen för loggbearbetning{#editing-the-log-processing-configuration-file}

Steg för att redigera filen Log Processing.cfg för en datauppsättningsprofil.

1. När du arbetar i datauppsättningsprofilen öppnar du [!DNL Profile Manager] och klickar på **[!UICONTROL Dataset]** för att visa innehållet.

   Mer information om hur du öppnar och arbetar med [!DNL Profile Manager] finns i *Datans Workbench användarhandbok*.

   >[!NOTE]
   >
   >Det kan finnas en underkatalog för loggbearbetning i datauppsättningskatalogen. Den här underkatalogen innehåller [!DNL Log Processing Dataset Include]-filerna som har skapats för en eller flera ärvda profiler. Se [Inkludera datauppsättningar](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Högerklicka på bockmarkeringen bredvid [!DNL Log Processing.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Fönstret [!DNL Log Processing.cfg] visas.

   Du kan också öppna [!DNL Log Processing.cfg]-filen från en [!DNL Transformation Dependency Map]. Mer information om omvandlingsberoendekartor finns i [Verktyg för datauppsättningskonfiguration](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Redigera parametrarna i konfigurationsfilen med följande tabell som hjälp.

   När du redigerar [!DNL Log Processing.cfg]-filen i ett data workbench-fönster kan du använda kortkommandon för grundläggande redigeringsfunktioner, inklusive klipp ut ( Ctrl+x ), kopiera ( Ctrl+C), klistra in ( Ctrl+V ), ångra ( Ctrl+z ), göra om ( Ctrl+Skift+z ), markera avsnitt (klicka+dra) och markera alla ( Ctrl+a ). Du kan också använda kortkommandona för att kopiera och klistra in text från en konfigurationsfil ( [!DNL .cfg]) till en annan.

   >[!NOTE]
   >
   >En [!DNL Log Processing Dataset Include]-fil för en ärvd profil innehåller en delmängd av parametrarna som beskrivs i följande tabell samt några ytterligare parametrar. Se [Inkludera datauppsättningar](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Beskrivning </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Loggkällor </td> 
      <td colname="col2"> Datakällor. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Loggkällor </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Sluttid </td> 
      <td colname="col2"> <p>Valfritt. Filtrera data för att inkludera loggposter med tidsstämplar fram till, men inte den här tiden. Adobe rekommenderar att du använder något av följande format för tillfället: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1 januari 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1 januari 2013 HH:MM:SS GMT </li> 
      </ul> <p>Om du till exempel anger 29 juli 2013 00:00:00 EDT som sluttid inkluderas data till och med 28 juli 2013, kl. 11:59:59 EDT. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datafilter </a>. </p> <p>Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench-servern finns i <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> <p>Obs!  Parametern Använd start-/sluttider för <span class="wintitle">-sensorn </span>, loggfilen och XML-källor är relaterade till den här parametern. Se de avsnitt i <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Loggkällor </a> som behandlar dessa källtyper. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fält </td> 
      <td colname="col2"> Valfritt. Adobe rekommenderar att du definierar <span class="wintitle"> fält </span> i en eller flera <span class="wintitle"> loggbearbetningsdatauppsättningar innehåller </span> filer. Se <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Loggbearbetningsdatauppsättning innehåller filer </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Högsta antal nyckelbyte för grupp </td> 
      <td colname="col2"> <p>Maximalt antal händelsedata som servern kan bearbeta för ett enda spårnings-ID. Data som överskrider denna gräns filtreras från datauppsättningens konstruktionsprocess. Det här värdet måste anges till 2e6 när tangentdelning är aktiv och 1e6 när tangentdelning inte är aktiv. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Nyckeldelning </a>. </p> <p> <p>Obs!  Ändra inte det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash-tröskelvärde </td> 
      <td colname="col2"> <p>Valfritt. En samplingsfaktor för slumpmässig delsampling av rader. Om värdet är ett tal n kommer endast ett av varje n spårnings-ID att matas in i datauppsättningen, vilket minskar det totala antalet rader i datauppsättningen med faktorn n. </p> <p>Om du vill skapa en datauppsättning som kräver 100 procents noggrannhet (d.v.s. att alla rader tas med) anger du ett hash-tröskelvärde. </p> <p>Värden: </p> <span class="filepath"> Hash-tröskelvärde = 1  </span> (100 procent av alla data inklusive alla rader.) <p> <span class="filepath"> Hash Threshold = 2  </span> (1/2 of data and includes half the rows.) </p> <p> <span class="filepath"> Hash-tröskelvärde = 3  </span>(1/3 av data och innehåller en av tre rader, men avrundas till 34 % vid Frågeslutförande) </p> <p> <span class="filepath"> Hash-tröskelvärde = 4  </span>(1/4 av data och innehåller en av fyra rader.) </p> <p> </p> <p> <p>Obs!  Om du använder ett Använda ett <span class="filepath"> hash-tröskelvärde = 8 </span> får du 1/8 av data, vilket är 12,5 %. Värdet <span class="uicontrol"> Frågeslutförande </span> avrundas till 13 % för det här värdet. Ytterligare exempel innehåller ett <span class="filepath"> hash-tröskelvärde = 6 </span> som ger en 17 % frågelösning. Ett <span class="filepath">-hash-tröskelvärde = 13 </span>resulterar i 8 % frågelösning. </p> </p> <p>Om <span class="wintitle">-hash-tröskelvärdet </span> anges i både <span class="filepath"> Log Processing.cfg </span>- och <span class="filepath"> Transformation.cfg </span>-filerna tillämpas det inte i sekvens. det högsta värde som anges i någon av konfigurationsfilerna gäller. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datafilter </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Loggpostvillkor </td> 
      <td colname="col2"> Valfritt. Definierar de regler som loggposter ska övervägas för att inkluderas i datauppsättningen. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Loggpostvillkor </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Återbearbeta </td> 
      <td colname="col2"> <p>Valfritt. Här kan du ange alla tecken eller teckenkombinationer. Om du ändrar den här parametern och sparar filen i data workbench Server-datorn initieras dataombearbetningen. </p> <p>Se <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Återbearbetning och omformning </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bucket Space </td> 
      <td colname="col2"> <p>Parametern är involverad i nyckeldelning. Dess värde ska vara 6e6 när nyckeldelning är aktiv. Se <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Nyckeldelning </a>. </p> <p> <p>Obs!  Ändra inte det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dela nyckelbyte </td> 
      <td colname="col2"> <p>Parametern är involverad i nyckeldelning. Dess värde bör vara 1e6 när tangentdelning är aktiv och 0 när tangentdelning inte är aktiv. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Nyckeldelning </a>. </p> <p> <p>Obs!  Ändra inte det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dela nyckelutrymmesförhållande </td> 
      <td colname="col2"> <p>Parametern är involverad i nyckeldelning. Värdet ska vara 10 när nyckeldelning är aktiv. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Nyckeldelning </a>. </p> <p> <p>Obs!  Ändra inte det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Steg </td> 
      <td colname="col2"> <p>Valfritt. Namnen på bearbetningsfaserna som kan användas i <span class="wintitle">-loggbehandlingsdatauppsättningen innehåller </span>-filer. Bearbetningsfaserna är ett sätt att ordna de omformningar som definieras i <span class="wintitle"> loggbearbetningsdatauppsättningen innehåller </span>-filer. Den här parametern är mycket användbar om du har definierat en eller flera omformningar i flera <span class="wintitle">-loggbehandlingsdatauppsättningar, inklusive </span>-filer, och du vill att specifika omformningar ska utföras vid specifika punkter under loggbearbetningen. </p> <p>Den ordning i vilken du listar de olika stegen här avgör i vilken ordning omformningarna i <span class="wintitle">-loggbehandlingsdatauppsättningen inkluderar </span>-filer körs under loggbearbetningen. Förbehandling och Postprocessing är inbyggda steg. Förbehandling är alltid det första steget och Postprocessing är alltid det sista steget. Som standard finns det en scen med namnet Default. </p> <p> <b>Lägga till en ny bearbetningsfas</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">I fönstret <span class="filepath"> Log Processing.cfg </span> högerklickar du på <span class="uicontrol"> Stages </span> och klickar på <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Ange ett namn för den nya scenen. </li> 
      </ul> </p> <p> <b>Ta bort en befintlig bearbetningsfas</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Högerklicka på numret för den scen som du vill ta bort och klicka på <span class="uicontrol"> Ta bort </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Obs!  När du anger en <span class="wintitle">-scen </span> i en <span class="wintitle">-logg som innehåller </span>-filer måste namnet på scenen matcha exakt det namn du anger här. Se <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Datauppsättningen innehåller filer </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Starttid </td> 
      <td colname="col2"> <p>Valfritt. Filtrera data för att inkludera loggposter med tidsstämplar vid eller efter den här tidpunkten. Adobe rekommenderar att du använder något av följande format för tillfället: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1 januari 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1 januari 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Om du till exempel anger"29 juli 2013 00:00:00 EDT" som starttid inkluderas data från och med 29 juli 2013, kl. 12:00:00 EDT. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datafilter </a>. </p> <p> Du måste ange en tidszon. Tidszonen får inte standardvärdet GMT om den inte anges. En lista över förkortningar av tidszoner som stöds av data workbench-servern finns i <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder </a>. </p> <p> <p>Obs!  Parametern Använd start-/sluttider för <span class="wintitle">-sensorn </span>, loggfilen och XML-källor är relaterade till den här parametern. Se de avsnitt i <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Loggkällor </a> som behandlar dessa källtyper. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Tidszon </td> 
      <td colname="col2"> <p>Valfritt. Tidszon för den data workbench-server som används för tidskonverteringar (till exempel den konvertering som representeras av fältet x-local-timestring) under loggbearbetningen. </p> <p> <p>Obs!  Du måste ange tidszonen om du vill komma åt det konverterade tidsfältet under loggbearbetningsfasen för datauppsättningens konstruktion. Annars registreras ett fel i händelseloggarna på data workbench-servern. </p> </p> <p>Se <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Tidszoner </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Omformningar </td> 
      <td colname="col2"> Valfritt. Adobe rekommenderar att du definierar transformeringar för loggbearbetning i en eller flera <span class="wintitle"> loggbehandlingsdatauppsättningar som innehåller </span> filer. Se <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Loggbearbetningsdatauppsättning innehåller filer </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. I [!DNL Profile Manager] högerklickar du på bockmarkeringen för [!DNL Log Processing.cfg]i [!DNL User]-kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* för att ändringarna ska börja gälla lokalt. Ombearbetningen av data börjar efter synkronisering av datauppsättningsprofilen.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

   Mer information om hur du ombearbetar data finns i [Återbearbetning och omformning](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
