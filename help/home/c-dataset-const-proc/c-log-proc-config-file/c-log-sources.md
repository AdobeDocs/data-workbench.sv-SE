---
description: Loggkällor är filer som innehåller de data som ska användas för att skapa en datauppsättning.
title: Loggkällor
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 0%

---

# Loggkällor{#log-sources}

Loggkällor är filer som innehåller de data som ska användas för att skapa en datauppsättning.

De data som är tillgängliga i loggkällorna kallas händelsedata eftersom varje datapost representerar en transaktionspost eller en enda instans av en händelse. Data Workbench-servern kan bearbeta loggkällor som härleds från data som samlats in av [!DNL Sensors] eller extraherats från andra datakällor.

* **Data som samlats in av [!DNL Sensors]: ** Data som samlats in av [!DNL Sensors] från HTTP- och programservrar överförs till data workbench-servrar, som konverterar data till mycket komprimerade loggfiler ( [!DNL .vsl]). Se [Sensorfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Data extraherade av Insight Server:** Data Workbench-servern läser händelsedata som finns i platta filer, XML-filer eller ODBC-kompatibla databaser och använder dess avkodare för att extrahera de önskade elementen i data. Sådana händelsedata behöver inte vara minnesbaserade, men posterna som innehåller data måste innehålla ett spårnings-ID. Se [Loggfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [XML-loggkällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887) och [ODBC-datakällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**Lägga till en loggkälla**

1. Öppna [!DNL Log Processing.cfg] i data workbench.
1. Högerklicka på **[!UICONTROL Log Sources]** och klicka sedan på **[!UICONTROL Add New]**.

1. Välj något av följande:

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. De specifika parametrar som används för att definiera en datauppsättning varierar beroende på vilken typ av loggkälla som ska användas i datauppsättningens konfigurationsprocess. Ange de parametrar som anges i det avsnitt som motsvarar rätt loggkälla:

   * [Sensorfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [Loggfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [XML-loggkällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [ODBC-datakällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. När du har definierat loggkällan (och gjort ändringar i andra parametrar) i [!DNL Log Processing.cfg]-filen sparar du filen lokalt och sparar den i datauppsättningsprofilen på data workbench-servern.

   >[!NOTE]
   >
   >En data workbench-server [!DNL File Server Unit] kan ta emot och lagra [!DNL Sensor] filer, loggfiler och XML-filer och skicka dem till den data workbench-serverns [!DNL Data Processing Units] som konstruerar datauppsättningen. Se [Konfigurera en filserverenhet för Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   Du kan öppna konfigurationen för valfri loggkälla från en [!DNL Transformation Dependency Map]. Mer information om [!DNL Transformation Dependency Map] finns i [Verktyg för datauppsättningskonfiguration](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## Krav {#section-d5901a4872774ad5bd01a18db114f1f2}

Händelsedata som samlats in av [!DNL Sensors] från HTTP- och programservrar överförs till data workbench-servrar, som konverterar data till mycket komprimerade loggfiler ( [!DNL .vsl]). Filformatet [!DNL .vsl] hanteras av data workbench-servern och varje fil har ett namn i formatet:

ÅÅÅÅMMDD-*SENSORID*.VSL

där YYMMDD är filens datum, och *SENSORID* är det namn (tilldelat av din organisation) som anger vilka [!DNL Sensor] som har samlat in och överfört data till data-workbench-servern.

## Parametrar {#section-5c3f1e341c284486aeba3452057da7f3}

Följande parametrar är tillgängliga för [!DNL Sensor]-filer:

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Loggbanor </td> 
   <td colname="col2"> <p>Kataloger där <span class="filepath"> .vsl</span>-filerna lagras. Standardplatsen är loggkatalogen. En relativ sökväg refererar till installationskatalogen för data workbench-servern. </p> <p>Du kan använda jokertecken för att ange vilka <span class="filepath"> .vsl</span>-filer som ska bearbetas: 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> * matchar valfritt antal tecken </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? matchar ett enda tecken </li> 
     </ul> </p> <p> Loggsökvägen <span class="filepath"> Logs\*.vsl</span> matchar alla filer i loggkatalogen som slutar i <span class="filepath"> .vsl</span>. Loggsökvägen <span class="filepath"> Logs\*-SENSOR?.vsl</span> matchar filer i loggkatalogen med alla datum (YYYMMDD) och ett tecken efter SENSOR, som i SENSOR1. </p> <p> Om du vill söka i alla underkataloger för den angivna sökvägen måste du ange parametern Rekursiv till true. </p> <p> <p>Obs! Om filerna ska läsas från en data workbench-servers <span class="wintitle"> filserverenhet</span> måste du ange rätt URI(er) i parametern Loggsökvägar. URI:n <span class="filepath"> /Logs/*-*.vsl</span> matchar alla <span class="filepath"> .vsl</span>-filer i loggkatalogen. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurera en filserverenhet för Insight Server</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggserver </td> 
   <td colname="col2">Information (adress, namn, port o.s.v.) som krävs för att ansluta till en filserver. Om det finns en post i parametern Log Server tolkas <span class="wintitle">-loggsökvägarna</span> som URI:er. Annars tolkas de som lokala sökvägar. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurera en filserverenhet för Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggkälla-ID </td> 
   <td colname="col2"> <p>Den här parameterns värde kan vara vilken sträng som helst. Om ett värde anges kan du med den här parametern skilja loggposter från andra loggkällor för käll-ID eller riktad bearbetning. Fältet x-log-source-id fylls i med ett värde som identifierar loggkällan för varje loggpost. Om du till exempel vill identifiera loggposter från en <span class="wintitle">-sensor</span> med namnet VSensor01 kan du skriva <span class="filepath"> från VSensor01</span>, och strängen skickas till fältet x-log-source-id för varje loggpost från den källan. </p> <p> Mer information om x-log-source-id-fältet finns i <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Händelsedatapostfält</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> Sant eller falskt. Om värdet är true genomsöks alla underkataloger för varje sökväg som anges i <span class="wintitle"> loggsökvägar</span> efter filer som matchar det angivna filnamnet eller jokertecknet. Standardvärdet är false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd start-/sluttider </td> 
   <td colname="col2"> <p>Sant eller falskt. Om värdet är true och Starttid eller Sluttid anges, måste alla filer för den här loggkällan ha filnamn som börjar med datum i ISO-format (YYYMMDD). Det antas att varje fil innehåller data för en GMT-dag (t.ex. tidsintervallet från 000 GMT på en dag och till nästa dag 000 GMT). Om loggkällfilerna innehåller data som inte motsvarar en GMT-dag måste parametern anges till false för att undvika felaktiga resultat. </p> <p> <p>Obs! Som standard uppfyller <span class="filepath"> .vsl </span>filer som innehåller data som samlats in av <span class="wintitle"> Sensor</span> automatiskt de krav på namngivning och tidsintervall som beskrivs ovan. Om du ställer in den här parametern på true bearbetar Data Workbench-servern alltid data från filer vars namn innehåller ISO-datum som ligger mellan den angivna starttiden och sluttiden. Om du ställer in den här parametern på false läser data workbench-servern alla <span class="filepath"> .vsl</span>-filer under loggbearbetningen för att avgöra vilka filer som innehåller data inom intervallet Starttid och Sluttid. </p> </p> <p> Mer information om parametrarna Starttid och Sluttid finns i <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datafilter</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Använd inte konfigurationsparametrarna för [!DNL Sensor]-datakällor för att avgöra vilka loggposter i en loggfil som ska inkluderas i en datauppsättning. Ställ i stället in datakällan så att den pekar på alla loggfiler i en katalog. Använd sedan parametrarna Starttid och Sluttid på [!DNL Log Processing.cfg] för att avgöra vilka loggposter som ska användas när datauppsättningen skapas. Se [Datafilter](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

Filen som innehåller händelsedata måste uppfylla följande krav:

* Varje händelsedatapost i filen måste representeras av en rad.
* Fälten i en post måste avgränsas, vare sig de är tomma eller inte, med en ASCII-avgränsare. Data Workbench-servern kräver inte att du använder en specifik avgränsare. Du kan använda vilket tecken som helst som inte är ett radslutstecken och som inte visas någonstans i själva händelsedatan.
* Varje post i filen måste innehålla:

   * Ett spårnings-ID
   * En tidsstämpel

* Om du vill ange start- och sluttider för databearbetning måste varje filnamn ha formatet:

   * [!DNL YYYYMMDD-SOURCE.log]

   där *ÅÅÅMMDD* är GMT-dagen (Greenwich Mean Time) för alla data i filen och *KÄLLA* är en variabel som identifierar källan till data i filen.

   >[!NOTE]
   >
   >Kontakta Adobe Consulting Services för att få en recension av de loggfiler som du tänker införliva i datauppsättningen.

## Parametrar {#section-83a861ac24954d54bbb9530e4d8bf23c}

Parametrarna i följande tabell är tillgängliga för loggfilens loggkällor.

>[!NOTE]
>
>Bearbetningen av loggfilens loggkällor kräver ytterligare parametrar som är definierade i en [!DNL Log Processing Dataset Include]-fil, som innehåller en delmängd av parametrarna i en [!DNL Log Processing.cfg]-fil, samt särskilda parametrar för att definiera avkodare för extrahering av data från loggfilen. Mer information om hur du definierar avkodare för loggfilens loggkällor finns i [Textfilavkodargrupper](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Identifieraren för loggfilskällan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggbanor </td> 
   <td colname="col2"> <p>Kataloger där loggfilerna lagras. Standardplatsen är loggkatalogen. En relativ sökväg refererar till installationskatalogen för data workbench-servern. </p> <p> Du kan använda jokertecken för att ange vilka loggfiler som ska bearbetas: 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> * matchar alla tecken. </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? matchar ett enda tecken. </li> 
     </ul> </p> <p> Loggsökvägen <span class="filepath"> Loggar\*.log</span> matchar alla filer i loggkatalogen som slutar i <span class="filepath"> .log</span>. </p> <p> Om du vill söka i alla underkataloger för den angivna sökvägen måste du ange parametern Rekursiv till true. </p> <p> Om filerna ska läsas från en data workbench-servers <span class="wintitle"> filserverenhet</span> måste du ange rätt URI(er) i parametern Loggsökvägar. Till exempel matchar URI:n/loggarna/*.log</span> alla <span class="filepath"> .log</span>-filer i loggkatalogen. <span class="filepath"> Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurera en filserverenhet för Insight Server</a>. </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggserver </td> 
   <td colname="col2"> Information (adress, namn, port o.s.v.) som krävs för att ansluta till en filserver. Om det finns en post i parametern Log Server tolkas <span class="wintitle">-loggsökvägarna</span> som URI:er. Annars tolkas de som lokala sökvägar. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurera en filserverenhet för Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komprimerad </td> 
   <td colname="col2"> Sant eller falskt. Värdet ska vara true om de loggfiler som ska läsas av data workbench-servern är komprimerade gzip-filer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avkodargrupp </td> 
   <td colname="col2"> Namnet på textfilens avkodningsgrupp som ska användas i loggfilens loggkälla. Namnet måste matcha exakt namnet på motsvarande textfilsavkodningsgrupp som anges i filen <span class="wintitle"> Loggbearbetning av datauppsättning Inkludera</span>. Se <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Textfilsavkodargrupper</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggkälla-ID </td> 
   <td colname="col2"> <p>Den här parameterns värde kan vara vilken sträng som helst. Om ett värde anges kan du med den här parametern skilja loggposter från andra loggkällor för käll-ID eller riktad bearbetning. Fältet x-log-source-id fylls i med ett värde som identifierar loggkällan för varje loggpost. Om du till exempel vill identifiera loggposter från en loggfilskälla med namnet LogFile01 kan du skriva <span class="filepath"> från LogFile01</span>, och strängen skickas till fältet x-log-source-id för varje loggpost från den källan. </p> <p> Mer information om x-log-source-id-fältet finns i <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Händelsedatapostfält</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maskmönster </td> 
   <td colname="col2"> <p>Ett reguljärt uttryck med ett enda hämtade delmönster som extraherar ett konsekvent namn som används för att identifiera källan till en serie loggfiler. Endast filnamnet beaktas. Sökvägen och tillägget beaktas inte för matchning av reguljära uttryck. Om du inte anger ett <span class="wintitle">-maskmönster</span> genereras en mask automatiskt. </p> <p> För filerna <span class="filepath"> Logs\010105server1.log</span> och <span class="filepath"> Logs\010105server2.log</span> är <span class="wintitle"> maskmönstret</span> <code>[0-9]{6}(.*)</code>. Det här mönstret extraherar strängen "server1" eller "server2" från filnamnen ovan. </p> <p> Se <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Reguljära uttryck</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> Sant eller falskt. Om den här parametern är inställd på true genomsöks alla underkataloger för varje sökväg som anges i <span class="wintitle"> loggsökvägar</span> efter filer som matchar det angivna filnamnet eller jokerteckenmönstret. Standardvärdet är false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avvisa fil </td> 
   <td colname="col2"> Sökvägen och filnamnet för filen som innehåller loggposterna som inte uppfyller villkoren för avkodaren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd start-/sluttider </td> 
   <td colname="col2"> <p>Sant eller falskt. Om den här parametern är inställd på true och Starttid eller Sluttid anges, måste alla filer för den här loggkällan ha filnamn som börjar med datum i ISO-format (YYYMMDD). Det antas att varje fil innehåller data för en GMT-dag (t.ex. tidsintervallet från 000 GMT på en dag och till nästa dag 000 GMT). Om loggkällans filnamn inte börjar med ISO-datum, eller om filerna innehåller data som inte motsvarar en GMT-dag, måste den här parametern anges till false för att undvika felaktiga resultat. </p> <p> <p>Obs!  Om de krav på namngivning och tidsintervall som beskrivs ovan uppfylls för loggfilerna och du ställer in den här parametern på true, begränsar den angivna textfilens avkodningsgrupp läsningarna till de filer vars namn har ISO-datum som ligger mellan den angivna starttiden och sluttiden. Om du ställer in den här parametern på false läser data workbench-servern alla loggfiler under loggbearbetningen för att avgöra vilka filer som innehåller data inom intervallet Starttid och Sluttid. </p> </p> <p> Mer information om parametrarna Starttid och Sluttid finns i <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datafilter</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet består datauppsättningen av två typer av loggkällor.

Loggkälla 0 anger loggfiler som genererats från händelsedata som hämtats av [!DNL Sensor]. Den här datakällan pekar på en katalog med namnet Logs och på alla filer i den katalogen med filnamnstillägget [!DNL .vsl].

Loggkälla 1 pekar på alla filer i loggkatalogen med filnamnstillägget [!DNL .txt]. Avkodningsgruppen för den här loggkällan kallas&quot;Textloggar&quot;.

![](assets/cfg_LogProcessing_LogSources.png)

Du bör inte ta bort eller flytta loggfiler när datakällorna för en datauppsättning har definierats. Endast nyligen skapade loggfiler ska läggas till i katalogen för datakällorna.

<!--
c_xml_log_sources.xml
-->

Filen som innehåller händelsedata måste uppfylla följande krav:

* Händelsedata måste inkluderas i en korrekt formaterad XML-fil med lämpliga överordnade och underordnade relationer.
* Det måste finnas en unik avkodningsgrupp för varje XML-filformat. Mer information om hur du skapar en avkodningsgrupp finns i [XML-avkodningsgrupper](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* Varje besökspost i filen måste innehålla:

   * Ett spårnings-ID
   * En tidsstämpel

* Om du vill ange start- och sluttider för databearbetning måste varje filnamn ha formatet

[!DNL YYYYMMDD-SOURCE.log]

där *ÅÅÅMMDD* är GMT-dagen (Greenwich Mean Time) för alla data i filen och *KÄLLA* är en variabel som identifierar källan till data i filen.

Ett exempel på en XML-fil som uppfyller dessa krav finns i [XML-avkodningsgrupper](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>Kontakta Adobe Consulting Services för att få en recension av de XML-loggfiler som du tänker införliva i datauppsättningen.

## Parametrar {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

För XML-loggkällor är parametrarna i följande tabell tillgängliga.

>[!NOTE]
>
>Bearbetningen av XML-loggkällor kräver ytterligare parametrar som är definierade i en [!DNL Log Processing Dataset Include]-fil, som innehåller en delmängd av parametrarna i en [!DNL Log Processing.cfg]-fil, samt särskilda parametrar för att definiera avkodare för extrahering av data från XML-filen. Mer information om hur du definierar avkodare för XML-loggkällor finns i [XML-avkodargrupper](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Identifieraren för XML-loggkällan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggbanor </td> 
   <td colname="col2"> <p>Kataloger där XML-loggkällor lagras. Standardplatsen är loggkatalogen. En relativ sökväg refererar till installationskatalogen för data workbench-servern. </p> <p> Du kan använda jokertecken för att ange vilka XML-loggkällor som ska bearbetas: 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> * matchar valfritt antal tecken </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? matchar ett enda tecken </li> 
     </ul> </p> <p>Loggsökvägen <span class="filepath"> Loggar\*.xml</span> matchar alla filer i loggkatalogen som slutar i <span class="filepath"> .xml</span>. </p> <p> Om du vill söka i alla underkataloger för den angivna sökvägen måste du ange värdet true i fältet <span class="wintitle"> Rekursiv</span>. </p> <p> <p>Obs! Om filerna ska läsas från en data workbench-servers <span class="wintitle"> filserverenhet</span> måste du ange rätt URI i fältet <span class="wintitle"> Loggsökvägar</span>. Till exempel matchar URI/loggar/*.xml</span> alla <span class="filepath"> .xml</span>-filer i katalogen Logs. <span class="filepath"> Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurera en filserverenhet för Insight Server</a>. </span></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggserver </td> 
   <td colname="col2"> Information (adress, namn, port o.s.v.) som krävs för att ansluta till en filserver. Om det finns en post i fältet <span class="wintitle"> Loggserver</span> tolkas <span class="wintitle"> Loggsökvägar</span> som URI:er. Annars tolkas de som lokala sökvägar. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurera en filserverenhet för Insight Server</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komprimerad </td> 
   <td colname="col2"> Sant eller falskt. Värdet ska vara true om de XML-loggkällor som ska läsas av data workbench-servern är komprimerade GZIP-filer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avkodargrupp </td> 
   <td colname="col2"> Namnet på XML-avkodningsgruppen som ska användas i XML-loggkällan. Namnet måste matcha exakt namnet på motsvarande XML-avkodningsgrupp som anges i filen <span class="wintitle"> Loggbearbetning av datauppsättning Inkludera</span>. Se <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML-avkodningsgrupper</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggkälla-ID </td> 
   <td colname="col2"> <p>Fältets värde kan vara vilken sträng som helst. Om ett värde anges kan du använda det här fältet för att skilja loggposter från olika loggkällor för käll-ID eller riktad bearbetning. Fältet x-log-source-id fylls i med ett värde som identifierar loggkällan för varje loggpost. Om du till exempel vill identifiera loggposter från en loggfilskälla med namnet XMLFile01 kan du skriva <span class="filepath"> från XMLFile01</span>, och strängen skickas till fältet x-log-source-id för varje loggpost från den källan. </p> <p> Mer information om x-log-source-id-fältet finns i <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Händelsedatapostfält</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maskmönster </td> 
   <td colname="col2"> <p>Ett reguljärt uttryck med ett enda hämtade delmönster som extraherar ett konsekvent namn som används för att identifiera källan till en serie loggfiler. Endast filnamnet beaktas. Sökvägen och tillägget beaktas inte för matchning av reguljära uttryck. Om du inte anger ett <span class="wintitle">-maskmönster</span> genereras en mask automatiskt. </p> <p> För filerna <span class="filepath"> Logs\010105server1.xml</span> och <span class="filepath"> Logs\010105server2.xml</span> är maskmönstret <code>[0-9]{6}(.*)</code>. Det här mönstret extraherar strängen "server1" eller "server2" från filnamnen ovan. </p> <p> Se <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> Reguljära uttryck</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rekursiv </td> 
   <td colname="col2"> Sant eller falskt. Om den här parametern är inställd på true genomsöks alla underkataloger för varje sökväg som anges i <span class="wintitle"> loggsökvägar</span> efter filer som matchar det angivna filnamnet eller jokerteckenmönstret. Standardvärdet är false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avvisa fil </td> 
   <td colname="col2"> Sökvägen och filnamnet för filen som innehåller loggposterna som inte uppfyller villkoren för avkodaren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd start-/sluttider </td> 
   <td colname="col2"> <p>Sant eller falskt. Om den här parametern är inställd på true och Starttid eller Sluttid anges, måste alla filer för den här loggkällan ha filnamn som börjar med datum i ISO-format (YYYMMDD). Det antas att varje fil innehåller data för en GMT-dag (t.ex. tidsintervallet från 000 GMT på en dag och till nästa dag 000 GMT). Om loggkällans filnamn inte börjar med ISO-datum, eller om filerna innehåller data som inte motsvarar en GMT-dag, måste den här parametern anges till false för att undvika felaktiga resultat. </p> <p> <p>Obs!  Om de krav på namngivning och tidsintervall som beskrivs ovan uppfylls för XML-filerna och du ställer in den här parametern på true, begränsar den angivna XML-avkodningsgruppen filerna till de filer vars namn har ISO-datum som ligger mellan den angivna starttiden och sluttiden. Om du ställer in den här parametern på false läser data workbench-servern alla XML-filer under loggbearbetningen för att avgöra vilka filer som innehåller data inom intervallen Starttid och Sluttid. </p> </p> <p> Mer information om parametrarna Starttid och Sluttid finns i <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datafilter</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Du bör inte ta bort eller flytta XML-loggkällor när datakällorna för en datauppsättning har definierats. Endast nyskapade XML-filer ska läggas till i katalogen för datakällorna.

<!--
AVRO-log-file.xml
-->

Avro-dataflödet är ett effektivare sätt att integrera data i Datan Workbench:

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro har ett format för trafik- och handelsdata som kan användas som en enda källa.
* Avro-flödet är komprimerade data för flera källsegment som tillhandahålls per dag. Det tillhandahåller endast ifyllda fält och övervaknings- och meddelandefunktioner, tillgång till historiska data samt automatisk återställning.
* Schemat, som är en självdefinierande layout för Avro-loggfiler, inkluderas i början av varje fil.
* Nya fält läggs till med stödinformation för import av Data Workbench utan att några ändringar behöver göras i avkodaren. Bland dessa finns:

   * Evars: 1-250 (tidigare 1-75)
   * Anpassade händelser: 1-1000 (jämfört med 1-100)
   * Tillgång till lösningsvariabler för mobil-, social- och videodata

>[!NOTE]
>
>Med hjälp av Avro-flödet får du dessutom omedelbar åtkomst till nya fält i feeden utan att användaren stänger av den, vilket gör att fälten kan uppdateras utan att någon arbetstidstid krävs.

Avro-dataflödet ställs in i separata filer:

* En **Avro-loggfil**: Det här är Avro-loggformatet som genereras från avkodaren för att formatera trafik- och handelsdata.
* En **Avro Decoder-fil**: Med den här filen kan du mappa värden till det nya Avro-formatet. Du kan ställa in avkodaren med Avro Decoder Wizard.

## Avro Decoder Wizard {#section-9a824b4c3d5549e7952a7111232035b2}

Den här guiden konfigurerar Avro-avkodarens loggfil.

Om du vill öppna högerklickar du i en arbetsyta och väljer **Admin** > **Guider** > **Avro Decoder Wizard**.

**Steg 1:** **Välj en Avro-loggfil**.

I det här steget kan du välja en källfil för Avro-schemat. Scheman kan nås från en loggfil (.log) eller en befintlig avkodningsfil (.avro). Scheman kan hämtas från båda filerna.

| **Avro-loggfil ** | Klicka för att öppna en loggfil (.log) och visa schemat högst upp i loggfilen och generera avkodningsfilen. |
|---|---|
| **Avro Decoder-fil** | Klicka för att öppna och redigera schemat för en befintlig avkodningsfil (.avro). |

**Steg 2: Välj Indatafält**.

Välj de inmatningsfält som ska användas i datauppsättningen för att gå igenom loggbearbetningen. Alla fält i filen visas så att du kan välja fält för feeden.

>[!NOTE]
>
>Ett [!DNL x-product(Generates row)]-fält anges om en matris påträffas i data. Det här fältet genererar nya rader för kapslade data i en array som indatafält. Om du till exempel har en Träff-rad med många produktvärden i en array, kommer rader att genereras i indatafilen för varje produkt.

| **Välj standardvärden** | Välj fält som ska identifieras som en standarduppsättning av standardfält. |
|---|---|
| **Markera alla** | Markera alla fält i filen. |
| **Avmarkera allt** | Rensa alla fält i filen. |

**Steg 3: Välj fält som kopieras för att generera rader.**

Eftersom nya rader kan skapas från kapslade värden i en array, måste alla nya rader som skapas ha ett spårnings-ID och en tidsstämpel. I det här steget kan du markera de fält som ska kopieras till rader från den överordnade posten, till exempel ett spårnings-ID och en tidsstämpel. Du kan också välja andra värden som du vill lägga till på varje rad.

| **Välj standardvärden** | Välj en standarduppsättning med standardfält som kräver nya kolumnvärden som läggs till på varje rad, till exempel ett spårnings-ID och en tidsstämpel. Ett [!DNL hit_source]-fält är till exempel ett standardvärde som måste läggas till i varje ny rad (det definieras som ett standardvärde i listan). Du kan lägga till andra kolumnvärden till varje rad efter behov. |
|---|---|
| **Markera alla** | Markera alla fält i filen. |
| **Avmarkera allt** | Rensa alla fält i filen. |

Använd rutan **Sök** för att hitta värden i listan.

**Steg 4: Ange avkodarens namn**

Ge fältgruppen ett namn och spara som en avkodningsfil. Namnet måste matcha namnet på avkodargruppen som anges i loggkällan.

**Steg 5: Spara avkodningsfilen.**

Filmenyn öppnas för att ge avkodningsfilen ett namn och sparas som en [!DNL .cfg]-fil i mappen **Loggar**.
