---
description: Data Workbench-servern (InsightServer64.exe) kan läsa händelsedata från alla SQL-databaser (till exempel Oracle eller Microsoft SQL Server) som har en ODBC 3.0-kompatibel drivrutin.
solution: Analytics
title: ODBC-datakällor
topic: Data workbench
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# ODBC-datakällor{#odbc-data-sources}

Data Workbench-servern (InsightServer64.exe) kan läsa händelsedata från alla SQL-databaser (till exempel Oracle eller Microsoft SQL Server) som har en ODBC 3.0-kompatibel drivrutin.

Data Workbench-serverns ODBC-stöd liknar det befintliga stödet för inläsning av data från sensorer eller från loggfiler som genereras av externa processer. Det finns dock några andra överväganden och begränsningar:

* Data Workbench-serverns ODBC-stöd är kompatibelt med klusterfunktionerna. Data distribueras till alla bearbetningsservrar och alla efterföljande bearbetningar (inklusive frågebearbetning) har full nytta av klustring.
* ODBC-stöd är beroende av ODBC-drivrutiner från tredje part. För att ODBC-stödet ska fungera måste dessa drivrutiner konfigureras på datorn som data workbench-servern körs på, med verktyg som inte finns på Adobe-plattformen. Datasökdatorer kräver ingen ytterligare konfiguration.
* Tabellen eller vyn som data läses in från måste ha en ökande ID-kolumn. För alla rader får värdet i den här kolumnen (som kan vara en faktisk kolumn i tabellen eller ett SQL-kolumnuttryck) inte minska när nya rader infogas i databasen. Om den här begränsningen överträds går data förlorade. För att prestanda ska bli bra krävs ett index för den här kolumnen eller kolumnuttrycket.

   >[!NOTE]
   >
   >Det är möjligt att flera rader har samma värde i [!DNL Increasing ID] kolumnen. En möjlighet är en tidsstämpelkolumn med mindre precision än perfekt.

* Data Workbench-servern kan inte läsa in kolumner med långa data (data över en viss längd som bestäms av det specifika databasprogram som används).
* Det tar längre tid att hämta data från en databas än att läsa dem från en diskfil. Datauppsättningar som läser in data från en ODBC-källa tar mycket längre tid att bearbeta (särskilt vid ombearbetning) än datauppsättningar med motsvarande storlek, vars data kommer från sensorer eller andra diskfiler.

Mer information om hur du bearbetar data finns i [Återbearbetning och omformning](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**Konfigurera Insight Server för ODBC[!DNL event data]**

När du konfigurerar data workbench-servern för att läsa in data från en SQL-databas måste du först utföra följande steg i ordning:

1. Installera lämplig programvara för databasklient, inklusive en ODBC-drivrutin, på den data workbench-serverdator där datauppsättningen bearbetas.

   >[!NOTE]
   >
   >Om du läser in ODBC-händelsedata för bearbetning i ett datalägesserverkluster måste du installera databasklientprogramvaran på alla bearbetningsservrar i klustret. Information om hur du anger bearbetningsservrar i ett kluster finns i *Server Products Installation and Administration Guide*.

1. Konfigurera en datakälla med hjälp av administratören för ODBC-datakällan för Windows.

   Det är viktigt att notera att data workbench-servern (InsightServer64.exe) körs som en Windows-tjänst. Därför måste datakällan vanligtvis konfigureras som ett system-DSN i stället för ett användar-DSN för att data workbench-servern ska kunna använda den. Mer information om det här konfigurationssteget finns i dokumentationen för databasprogramvaran.

När du har installerat databasklientprogramvaran på rätt dator med en workbench-server kan du konfigurera datauppsättningen så att den använder ODBC-datakällan genom att redigera lämpliga parametrar i konfigurationsfilen för den profil du vill använda [!DNL Log Processing] .

## Parametrar {#section-15c0218d93364693a565f2609a12f73e}

Följande parametrar är tillgängliga för data från databaser som använder ODBC-standarden (Open Database Connectivity):

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Identifieraren för ODBC-källan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namn på datakälla </td> 
   <td colname="col2"> Ett DSN, som tillhandahålls av en administratör för den data workbench-serverdator på vilken datauppsättningen bearbetas, som refererar till den databas från vilken data ska läsas in. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Databaslösenord </td> 
   <td colname="col2"> Lösenordet som ska användas vid anslutning till databasen. Om ett lösenord har konfigurerats för DSN i administratören <span class="wintitle"> för</span>datakällan kan detta lämnas tomt. Lösenordet som anges här åsidosätter lösenordet som konfigurerats för DSN i administratören <span class="wintitle"> för</span>datakällan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Användar-ID för databas </td> 
   <td colname="col2"> Det användar-ID som ska användas vid anslutning till databasen. Om ett användar-ID har konfigurerats för DSN i administratören <span class="wintitle"> för</span>datakällan kan detta lämnas tomt. Alla användar-ID som anges här åsidosätter det användar-ID som konfigurerats för DSN i administratören <span class="wintitle"> för</span>datakälla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fält </td> 
   <td colname="col2"> En vektor med kolumnobjekt som anger en mappning från datakolumner i databasen till datafält i Data Workbench-serverns körningsmotor. Varje kolumn har posterna <span class="wintitle"> Kolumnnamn</span> och <span class="wintitle"> Fältnamn</span>. <span class="wintitle"> Kolumnnamn</span> är ett SQL-kolumnuttryck som måste vara giltigt i kontexten för den tabell som identifieras av <span class="wintitle"> tabellidentifieraren</span> som beskrivs ovan. Det kan vara ett kolumnnamn eller ett SQL-uttryck baserat på valfritt antal kolumner i tabellen. En formateringsfunktion kan behövas för att konvertera värden för vissa datatyper till strängar på ett sätt som inte förlorar precision. Alla data konverteras implicit till strängar med databasens standardformateringsmetod, som kan orsaka dataförlust för vissa kolumndatatyper (till exempel datatyper för datum/tid) om explicita formateringsuttryck inte används. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Öka ID-kolumn </td> 
   <td colname="col2"> <p>Ett kolumnnamn eller SQL-kolumnuttryck som uppfyller villkoret som det ökar (eller åtminstone inte minskar) när nya rader läggs till. Det vill säga, om rad B läggs till i tabellen vid en senare tidpunkt än rad A, måste värdet för den här kolumnen (eller kolumnuttrycket) i rad B vara större (enligt databasens ursprungliga sorteringsordning) än motsvarande värde i rad A. </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> Kolumnnamnet <span class="wintitle"> för Ökning av ID kan vara samma </span>som namnet på en befintlig kolumn, men måste inte vara det. </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> Det här uttrycket antas ha en SQL-teckendatatyp. Om den faktiskt ökande ID-kolumnen är av någon annan datatyp måste det här värdet vara ett kolumnuttryck för att konvertera det till en sträng. Eftersom detta vanligtvis innebär att jämförelser är lexikografiska (tecken för tecken) är det viktigt att formatera värdet noggrant. </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> Uttrycket används i SQL ORDER BY-satser och jämförs med i SQL WHERE-satser. Det är viktigt att ha ett index som bygger på det exakta kolumnuttryck som används. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggkälla-ID </td> 
   <td colname="col2"> <p>Den här parameterns värde kan vara vilken sträng som helst. Om ett värde anges kan du med den här parametern skilja loggposter från andra loggkällor för käll-ID eller riktad bearbetning. Fältet x-log-source-id fylls i med ett värde som identifierar loggkällan för varje loggpost. Om du till exempel vill identifiera loggposter från en ODBC-källa med namnet ODBCSource01 kan du skriva <span class="filepath"> från ODBCSource01.</span> och strängen skickas till x-log-source-id-fältet för varje loggpost från den källan. </p> <p> Mer information om x-log-source-id-fältet finns i <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Fält för händelsedatapost</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kör på server </td> 
   <td colname="col2"> Indexvärde i filen <span class="filepath"> profile.cfg</span> på bearbetningsservern som gör att ODBC-frågor hämtar data från databasen. (Parametern Processing Servers i filen <span class="filepath"> profile.cfg</span> listar alla bearbetningsservrar för datauppsättningen, och varje server har ett indexvärde som först är 0.) Standardvärdet är 0. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tabellidentifierare </td> 
   <td colname="col2"> Ett SQL-uttryck som namnger tabellen eller vyn som data ska läsas in från. En typisk tabellidentifierare har formen SCHEMA.TABLE. </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet visas konfigurationsfönstret [!DNL Log Processing] i data workbench med en ODBC-datakälla. Den här datakällan hämtar data från en tabell som kallas [!DNL VISUAL.VSL] i en databas med [!DNL Data Source Name] &quot;VSTestO&quot;. Fem (5) kolumnobjekt ( [!DNL Fields]) mappar data från datakolumnerna i databasen till data workbench-servern.

![](assets/cfg_LogProcessing_LogSources_ODBC.png)

