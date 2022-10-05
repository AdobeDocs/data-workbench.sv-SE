---
description: Exportörerna tillhandahåller instruktioner för hur händelsedata ska skrivas ut.
title: Definiera exporterare
uuid: 565d4482-6c25-407c-bda7-0d116180902a
exl-id: 5de6266a-e959-414c-9512-5e9f4011881b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 1%

---

# Definiera exporterare{#defining-exporters}

{{eol}}

Exportörerna tillhandahåller instruktioner för hur händelsedata ska skrivas ut.

Omformningsfunktionen tillhandahåller tre typer av exporterare för export [!DNL .vsl] filer, loggfiler, XML-filer och ODBC-data som [!DNL .vsl] filer, textfiler eller avgränsade textfiler som kan användas av inläsningsrutiner, revisionsbyråer eller andra mål för DataWarehouse.

>[!NOTE]
>
>För att en exportör ska kunna fungera på rätt sätt måste loggkällan uppfylla de tillämpliga krav som beskrivs i [Loggkällor](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) avsnitt i [Konfigurationsfil för loggbearbetning](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

**Definiera en exporterare**

1. Öppna [!DNL Transform.cfg] i data workbench. Se [Så här redigerar du filen Insight Transform.cfg](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13).
1. Högerklicka **[!UICONTROL Exporters]** och sedan klicka **[!UICONTROL Add New]**.
1. Välj något av följande alternativ:

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**

   >[!NOTE]
   >
   >För [!DNL ExportVSLFile] , alla utökade fält i indatafilen och alla användardefinierade fält i formuläret cs(*header*) skrivs alltid till VSL utdatafil. Om du skriver över ett befintligt utökat fält skrivs det nya värdet till utdatafilen, även om fältet är tomt.

1. Redigera exportörsparametrarna i konfigurationsfilen med hjälp av följande tabell som vägledning:

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Beskrivning </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> Dataformat </td> 
      <td colname="col2"> <p>För <span class="wintitle"> ExportTextFile</span> endast. Formatet för varje utdatarad, bestående av fältnamnsundantag (uttryckt i %)<i>fältnamn</i>%) och annan önskad fast text. Formatet bör innehålla en radavgränsare, vanligtvis [CR] [LF]. </p> <p> Ett literalt procenttecken (%) kan bäddas in i formatsträngen genom att undvika tecknet som visas här: %% </p> <p> Ett exempel på en post för parametern Data Format är <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Fält </td> 
      <td colname="col2">För <span class="wintitle"> ExportDelimitedTextFile</span> endast. Namn på de fält som ska skrivas ut. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Avgränsare </td> 
      <td colname="col2"> <p>Valfritt. För <span class="wintitle"> ExportDelimitedTextFile</span> endast. Tecken som används för att separera fälten i utdatafilen. </p> <p> Programvaran kan inte kringgå avgränsare som ingår i datavärdena. Därför rekommenderar Adobe inte att du använder kommatecken som avgränsare. </p> <p> Om du håller ned Ctrl-tangenten och högerklickar i parametern Avgränsare visas ett <span class="wintitle"> Infoga</span> visas. Den här menyn innehåller en lista med specialtecken som ofta används som avgränsare. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Radavgränsare </td> 
      <td colname="col2">Valfritt. För <span class="wintitle"> ExportDelimitedTextFile</span> endast. Tecknet/tecknen som används för att avgränsa rader i utdatafilerna. Standardvärdet är [CR] [LF]. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Namn </td> 
      <td colname="col2"> <p>Valfritt. Identifierare för exportören. Det här namnet visas i dialogrutan <span class="wintitle"> Detaljerad status</span> gränssnitt. </p> <p> Mer information om <span class="wintitle"> Detaljerad status</span> -gränssnittet finns i <i>Användarhandbok för Data Workbench</i>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Kommentarer </td> 
      <td colname="col2"> Valfritt. Noteringar om exportören. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Utdatasökväg </td> 
      <td colname="col2"> <p>Sökväg där utdatafiler ska lagras. Sökvägen är relativ till installationsmappen för data workbench-servern. </p> <p> <p>Obs! Data Workbench-servern som lagrar utdata bearbetar servern #0 i <span class="filepath"> profile.cfg</span> -fil. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Filrotationsperiod </td> 
      <td colname="col2"> <p>Valfritt. Den frekvens som data exporteras till utdatafilen. Varje utdatafil innehåller data som hör till en viss tidsperiod som kallas rotationsperiod. Alla tidsberäkningar görs i GMT: En dag börjar vid midnatt GMT och slutar följande dag vid midnatt GMT, även om de data som skrivs till filen innehåller ett fält som har omvandlats till lokal tid. </p> <p> Tillgängliga värden är följande: </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> ÅR. Varje fil innehåller data för ett kalenderår. </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MÅNAD. Varje fil innehåller data för en kalendermånad. Månader är numrerade 1 (januari) till 12 (december). </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> VECKA. Varje fil innehåller data för en vecka. En vecka börjar på måndag. Den vecka som börjar på en av de första sju dagarna av året är vecka 1 och den föregående (partiella) veckan, om någon, är vecka 0. </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> DAG. Varje fil innehåller data för en kalenderdag. </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> TIMME. Varje fil innehåller data i en timme. </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> INGEN. Ingen rotation utförs. Alla data skrivs till samma fil (eller en uppsättning filer som bestäms av andra parameterinställningar). Se <span class="wintitle"> Filnamnsformat</span> i den här tabellen. </li> 
      </ul> <p>Filrotationsperioden är som standard DAY. </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> Ställ bara in filrotationen på NONE när du arbetar i <span class="wintitle"> Offlineläge</span>. Se <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"> Offlineläge</a> parameterbeskrivning. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Filnamnsformat </td> 
      <td colname="col2"> <p>Valfritt. Formatet på utdatafilens namn. </p> <p> Varje loggpost kan lagras i en fil vars namn härleds från rotationsperiodens starttid, och eventuellt från värden i fälten på raderna som den innehåller. De fält som ska användas i filnamnet bäddas in som fältnamn kan rymmas (uttryckt som %)<i>fältnamn</i>%). </p> <p>Filnamnskomponenterna som är relaterade till rotationsperioden är inbäddade i formatsträngen med följande escape-sekvenser: 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy% (fyrsiffrigt år) </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy% (tvåsiffrigt år) </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm% (tvåsiffrig månad, 01-12) </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww% (tvåsiffrig vecka, 01-52) </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd% (tvåsiffrig dag, 01-31) </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH% (tvåsiffrig timme, 00-23) </li> 
      </ul> </p> <p> Standardfilnamnsformatet är <span class="filepath"> %yyyy%%mm%%dd%-%x-mask%.txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> Escape-sekvenserna är skiftlägeskänsliga. </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> Om filrotationsperioden är NONE ersätts en tom sträng för varje escape-sekvens, om sådan finns. </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> Ett fel genereras om <span class="wintitle"> Filnamnsformat</span> resulterar inte i ett unikt filnamn för varje rotationsperiod (se parametern Filrotationsperiod i den här tabellen). Om du t.ex. använder DAGS-rotationsperioden måste escape-sekvenserna %dd%, %mm% och %yy% eller %yyyy% finnas i mönstret för att undvika dataförlust. </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> Om du använder escape-sekvenser för fältnamn i mönstret och det angivna fältet har många distinkta värden, skrivs många utdatafiler för varje rotationsperiod. Observera att det här scenariot kan ge sämre prestanda, så du bör använda den här funktionen med försiktighet. </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> Alla beräkningar görs i GMT. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Kör vid överrullning </td> 
      <td colname="col2"> <p>Valfritt. När varje fil är klar kan ett externt (Windows) kommando köras. Kommandoraden hämtas från det slutliga filnamnet genom att ersätta följande escape-sekvenser med den här parametern: </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%. Katalogdelen av det slutliga filnamnet, inklusive det avslutande omvända snedstrecket. </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%. Den slutliga filens filnamn (exklusive katalogen och filnamnstillägget). </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%. Tillägget (inklusive inledande ".") för det slutliga filnamnet. </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %path%. Filens fullständiga sökvägsnamn, vilket motsvarar %dir%%file%%ext%. </li> 
      </ul> <p> Som standard är den här parametern tom (inget kommando körs). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Minnesgräns </td> 
      <td colname="col2"> <p>Valfritt. Mängden minne i byte som används för buffring av exportörens utdata. Standardvärdet är 10 000 000 byte. </p> <p> <p>Obs! Om du har många utdatafiler som är öppna samtidigt kanske du vill öka det här värdet, men du kan minska mängden tillgängligt minne för andra komponenter i systemet. Om du minskar värdet kan dock exportprocessen gå långsammare. Kontakta Adobe om du behöver hjälp. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Gräns för öppna filer </td> 
      <td colname="col2"> <p>Valfritt. Det maximala antalet filer som kan vara öppna samtidigt för utdata från exporteraren. Om det här antalet överskrids registreras ett fel i händelseloggen och data workbench-servern slutar att köras. Standardvärdet är 1 000. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. När du har definierat din exportör (och ändrat andra parametrar) i dialogrutan [!DNL Transform.cfg] sparar du filen lokalt och sparar den i lämplig profil på datorn med en data workbench-server.
