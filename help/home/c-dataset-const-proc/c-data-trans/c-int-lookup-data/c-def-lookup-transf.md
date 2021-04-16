---
description: Information om de omvandlingar som du kan använda för att lägga in sökdata i datauppsättningen.
title: Definiera uppslagsomformningar
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 1%

---

# Definiera uppslagskonverteringar{#defining-lookup-transformations}

Information om de omvandlingar som du kan använda för att lägga in sökdata i datauppsättningen.

Observera att inte alla typer kan användas under båda faserna av datauppsättningskonstruktionsprocessen.

* [Kategorisera](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Kategorisera {#section-8474376c14e54d14ae73749696ada468}

I [!DNL Categorize]-omformningen används en uppslagstabell med två kolumner som består av mönstersträng/värdepar. Under den här omvandlingen läser data workbench-servern i sin tur varje händelsedatapost och jämför innehållet i ett visst fält i posten med alla mönstersträngar som listas i den första kolumnen i uppslagstabellen. Om det angivna fältet matchar en av mönstersträngarna skriver data workbench-servern det värde (som finns i den andra kolumnen) som är associerat med den mönstersträngen till ett angivet utdatafält i posten.

Strängarna i den första kolumnen i uppslagstabellen kan börja med tecknet ^ och/eller sluta med tecknet $ för att tvinga fram matchning i början och/eller slutet. Den här omformningen accepterar inte reguljära uttryck för att definiera matchningsvillkor i den första kolumnen. Om indatavärdet är en vektor med strängar, körs varje sträng genom omformningen och resultatet(en) läggs till i en utdatasträngsvektor.

En [!DNL Categorize]-omformning är i allmänhet enklare och snabbare än att använda en [!DNL Regular Expression]-omformning för att uppnå samma sak.

>[!NOTE]
>
>Delsträngstestet som används i [!DNL Categorize] är skiftlägeskänsligt om inte annat anges med parametern [!DNL Case Sensitive].

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Beskrivande namn på omformningen. Här kan du ange valfritt namn. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skiftlägeskänslig </td> 
   <td colname="col2"> Sant eller falskt. Anger om delsträngstestet är skiftlägeskänsligt. </td> 
   <td colname="col3"> sant </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om omvandlingen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor som den här omformningen används under. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Standardvärdet som ska användas om villkorstestet lyckas och ingen post i kategoriseringsfilen matchar indata, eller om indatafältet inte är definierat i den angivna loggposten. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avgränsare </td> 
   <td colname="col2"> <p>Sträng som används för att separera kolumnerna i sökfilen. Måste vara ett enda tecken långt. </p> <p> Om du håller ned Ctrl-tangenten och högerklickar i avgränsarparametern visas en <span class="wintitle"> Infoga</span>-meny. Den här menyn innehåller en lista med specialtecken som ofta används som avgränsare. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Flera värden </td> 
   <td colname="col2"> Sant eller falskt. Om värdet är true, när flera rader i filen matchar indata, resulterar varje rad i att ett värde läggs till i utdatavektorn för strängar. Om värdet är false används endast den första matchande raden i filen i utdata. I det senare fallet, om indata är en vektor, är utdata även en vektor med samma längd. Om indata är en enkel sträng är utdata också en enkel sträng. </td> 
   <td colname="col3"> falskt </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fil </td> 
   <td colname="col2"> Kategoriseringsfilens sökväg och filnamn. Relativa sökvägar gäller installationskatalogen för data workbench-servern. Den här filen finns vanligtvis i katalogen Lookups i installationskatalogen för data workbench-servern. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Kategoriseringsfilen matchar delsträngarna mot värdet i det här fältet för att identifiera den matchande raden i filen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> Namnet på fältet som är associerat med resultatet. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Att tänka på vid kategorisering**

* Ändringar av sökfiler i [!DNL Categorize]-omformningar som definieras i [!DNL Transformation.cfg]-filen eller i en [!DNL Transformation Dataset Include]-fil kräver omformning av datauppsättningen. Uppslagsfiler för [!DNL Categorize]-omformningar som definieras i [!DNL Log Processing.cfg]-filen eller en [!DNL Log Processing Dataset Include]-fil omfattas inte av den här begränsningen. Mer information om hur du ombearbetar data finns i [Återbearbetning och omformning](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] omformningar som definieras i  [!DNL Log Processing.cfg] filen eller en  [!DNL Log Processing Dataset Include] fil läser in sina sökfiler igen när sökfilerna ändras. Ändringarna tillämpas inte retroaktivt, men de gäller för alla loggdata som läses efter att ändringen har utförts.

I det här exemplet visas hur du använder [!DNL Categorize]-omvandlingen för att integrera sökdata med händelsedata som samlats in från webbplatstrafiken. Anta att en viss webbplats har affärssektioner och att det finns ett krav på att kunna titta på och jämföra utifrån trafikflödet och det värde som genereras av de olika sektionerna. Du kan skapa en uppslagsfil som listar de delsträngar som används för att identifiera de olika avsnitten.

Uppslagsfilen [!DNL Lookups\custommap.txt] innehåller följande tabell:

| /produkter/ | Produkter |
|---|---|
| ^/sport/ | Idrott |
| ^/news/ | Nyheter |
| ... | ... |

Den här kategoriseringsfilen mappar allt som innehåller strängen &quot;/products/&quot; till värdet &quot;Products&quot;, allt från &quot;/sport/&quot; till värdet &quot;Sports&quot; och allt från &quot;/news/&quot; till värdet &quot;News&quot;. I följande kategoriseringsomformning används värdet i cs-uri-stam-fältet som strängen som vi söker efter en matchande delsträng i. Resultatet av omformningen placeras i fältet x-custom.

![](assets/cfg_TransformationType_Categorize.png)

Om parametern Multiple Values är inställd på false skulle exemplet generera följande värden för x-customap med de listade värdena för cs-uri-stam.

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Idrott |
| [!DNL /sports/products/buy.php] | Produkter |
| [!DNL /news/headlines.php] | Nyheter |
| [!DNL /news/products/subscribe.php] | Produkter |

Utdata baseras på ordningen för delsträngarna i uppslagsfilen. cs-uri-stam [!DNL /sports/products/buy.php] returnerar till exempel &quot;Produkter&quot;. Även om URI-stammen börjar med &quot;/sport/&quot; listas strängen &quot;/products/&quot; före &quot;/sport/&quot; i sökfilen. Om parametern Multiple Values hade värdet true skulle det finnas ytterligare ett värde för x-custom, eftersom det sista exemplet skulle matcha två rader i uppslagstabellen: Produkter och nyheter.

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

För [!DNL FlatFileLookup]-omformningen används en uppslagstabell som består av ett valfritt antal kolumner och rader (du bör dock komma ihåg att den finns i minnet). Under den här typen av omvandling läser data workbench-servern i sin tur varje händelsedatapost och jämför innehållet i ett visst fält i posten med vart och ett av värdena i en angiven kolumn i uppslagstabellen. Om det finns en matchning skriver data workbench-servern ett eller flera värden från matchande rad i uppslagstabellen till ett eller flera angivna utdatafält i händelsedataposten.

Uppslagstabellen som används under den här omformningen fylls i från en platt fil vars plats du anger när du definierar omformningen.

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Beskrivande namn på omformningen. Här kan du ange valfritt namn. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om omvandlingen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor som den här omformningen används under. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Standardvärdet som ska användas om villkoret är uppfyllt och om ingen post i uppslagsfilen matchar indata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avgränsare </td> 
   <td colname="col2"> <p>Sträng som används för att separera kolumnerna i sökfilen. Måste vara ett enda tecken långt. </p> <p> Om du håller ned Ctrl-tangenten och högerklickar i avgränsarparametern visas en <span class="wintitle"> Infoga</span>-meny. Den här menyn innehåller en lista med specialtecken som ofta används som avgränsare. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fil </td> 
   <td colname="col2"> Sökfilens sökväg och filnamn. Relativa sökvägar gäller installationskatalogen för data workbench-servern. Den här filen finns vanligtvis i katalogen Lookups i installationskatalogen för data workbench Server. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rubrikrad </td> 
   <td colname="col2"> Sant eller falskt. Anger att den första raden i tabellen är en rubrikrad som ska ignoreras vid bearbetningen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> <span class="wintitle"> Kolumnnamn är namnet </span> på den kolumn som används för att matcha indata med raden/raderna i filen. Om rubrikraden är true kan det vara namnet på en kolumn i sökfilen. Annars måste det vara det nollbaserade kolumnnumret som ska matchas mot. <span class="wintitle"> Fältnamn är namnet </span> på fältet som används för att hitta raden i sökfilen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Flera värden </td> 
   <td colname="col2"> <p>Sant eller falskt. Avgör om ett enskilt värde (en matchande rad) eller flera värden ska returneras (ett för varje matchande rad). </p> <p> <p>Obs!  Om <span class="wintitle"> Multiple Values</span> är false måste du se till att det inte finns flera matchningar. När flera matchningar inträffar finns det ingen garanti för vilken matchning som returneras. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> <p>En vektor med kolumnobjekt (resultat) där varje objekt definieras av kolumn- och fältnamn. </p> <p> <span class="wintitle"> Kolumnnamn är den kolumn som </span> utdatavärdet hämtas från. Om <span class="wintitle"> rubrikrad</span> är true kan det vara namnet på en kolumn i sökfilen. Annars måste det vara det nollbaserade kolumnnumret som ska matchas mot. </p> <p> <span class="wintitle"> Fältnamn är namnet </span> på fältet som används för att hämta utdata. Observera att detta kan vara en resultatvektor, en för varje rad som identifieras i det fall då parametern Multiple Values är true. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Att tänka på[!DNL FlatFileLookup]**

* Att matcha indatafältet med sökfilen är alltid skiftlägeskänsligt.
* Ändringar av sökfiler i [!DNL FlatFileLookup]-omformningar som definieras i [!DNL Transformation.cfg]-filen eller [!DNL Transformation Dataset Include]-filer kräver omformning av datauppsättningen. Uppslagsfiler för [!DNL FlatFileLookup]-omformningar som definieras i [!DNL Log Processing.cfg]-filen eller [!DNL Log Processing Dataset Include]-filerna omfattas inte av den här begränsningen. Mer information om hur du ombearbetar data finns i [Återbearbetning och omformning](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] omformningar i  [!DNL Log Processing.cfg] filen eller  [!DNL Log Processing Dataset Include] filerna läser in sina sökfiler igen när sökfilerna ändras. Ändringarna tillämpas inte retroaktivt, men de gäller för alla loggdata som läses efter att ändringen har utförts.

I det här exemplet visas hur du använder [!DNL FlatFileLookup]-omvandlingen för att integrera sökdata med händelsedata som samlats in från webbplatstrafiken. Anta att du vill isolera webbplatspartners som dirigerar trafik till webbplatsen och omvandla deras partner-ID:n till mer användarvänliga namn. Sedan kan du använda användarvänliga namn för att skapa utökade dimensioner och visualiseringar som tydligare kopplas till affärsrelationen än den relation mellan platser som används för att dirigera trafik.

Exempelomvandlingen söker i fältet cs(referrer-query) efter namnvärdespar för PartnerID, och om den finns används sökfilen [!DNL Lookups\partners.txt] för att jämföra PartnerID-värdet med värdena i kolumnen [!DNL Partner] i tabellen. Om det finns en rad får utdatafältet x-partner-name namnet från [!DNL PrintName]-kolumnen för den identifierade raden.

![](assets/cfg_TransformationType_FlatFileLookup.png)

Om uppslagstabellen innehåller följande information:

| ID | Partner | Startat | PrintName |
|---|---|---|---|
| 3 | P154 | 21 aug 1999 | Yahoo |
| 2 | P232 | 10 juli 2000 | Microsoft |
| 1 | P945 | 12 jan 2001 | Amazon |

Följande exempel omformas så här:

* Om cs(reference)(PartnerID) returnerade P232 får fältet x-partner-name värdet &quot;Microsoft&quot;.
* Om cs(reference)(PartnerID) returnerade P100 får fältet x-partner-name värdet &quot;Ingen partner&quot;.
* Om cs(referrer)(PartnerID) inte returnerade någonting får fältet x-partner-name värdet &quot;Ingen partner&quot; enligt parametern Default.

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

[!DNL ODBCLookup]-omformningen fungerar som en [!DNL FlatFileLookup]-omformning. Den enda skillnaden är att den uppslagstabell som används under omvandlingen fylls i från en ODBC-databas och inte en platt fil.

>[!NOTE]
>
>[!DNL ODBCLookup] omvandlingar kan bara utföras under datauppsättningens omformningsfas. När det är möjligt rekommenderar Adobe att du använder [!DNL FlatFileLookup]-omformningen i stället för [!DNL ODBCLookup]-omformningen. [!DNL FlatFileLookup] omvandlingar är i sig mer tillförlitliga eftersom de inte är beroende av tillgängligheten för ett externt system. Dessutom är risken mindre att uppslagstabellen ändras om den finns i en platt fil som du kontrollerar lokalt.

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Beskrivande namn på omformningen. Här kan du ange valfritt namn. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om omvandlingen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor som den här omformningen används under. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namn på datakälla </td> 
   <td colname="col2"> Ett DSN, som tillhandahålls av en administratör för den data workbench-serverdator på vilken datauppsättningen bearbetas, som refererar till den databas från vilken data ska läsas in. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Databaslösenord </td> 
   <td colname="col2">Lösenordet som ska användas vid anslutning till databasen. Om ett lösenord har konfigurerats för DSN i <span class="wintitle">-administratören för datakällan</span> kan detta lämnas tomt. Lösenordet som anges här åsidosätter lösenordet som konfigurerats för DSN i <span class="wintitle">-administratören för datakällan</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Användar-ID för databas </td> 
   <td colname="col2">Det användar-ID som ska användas vid anslutning till databasen. Om ett användar-ID har konfigurerats för DSN i <span class="wintitle">-administratören för datakällan</span> kan detta lämnas tomt. Alla användar-ID som anges här åsidosätter det användar-ID som konfigurerats för DSN i <span class="wintitle">-administratören för datakällan</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Det standardvärde som ska användas om villkoret är uppfyllt och ingen post i uppslagsfilen matchar indata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indatakolumn </td> 
   <td colname="col2"> <span class="wintitle"> Kolumnnamn är </span> kolumnnamnet eller SQL-uttrycket för data som matchas mot indata. <span class="wintitle"> Fältnamn är namnet </span> på fältet som innehåller data som ska slås upp. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Flera värden </td> 
   <td colname="col2"> <p>Sant eller falskt. Avgör om ett enskilt värde (en matchande rad) eller flera värden ska returneras (ett för varje matchande rad). </p> <p> <p>Obs!  Om <span class="wintitle"> Multiple Values</span> är false måste du se till att det inte finns flera matchningar. När flera matchningar inträffar finns det ingen garanti för vilken matchning som returneras. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdatakolumner </td> 
   <td colname="col2"> <p>En vektor med kolumnobjekt (resultat) där varje objekt definieras av kolumn- och fältnamn. </p> <p> <span class="wintitle"> Kolumnnamn är namnet </span> på eller SQL-uttrycket för den kolumn som utdatavärdet hämtas från. <span class="wintitle"> Fältnamn är namnet </span> på fältet som används för att hämta utdata. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tabellidentifierare</span> </td> 
   <td colname="col2"> Ett SQL-uttryck som namnger tabellen eller vyn som data ska läsas in från. En typisk tabellidentifierare har formen SCHEMA.TABLE. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* Datakällans namn, [!DNL Database User ID], [!DNL Database Password] och tabellidentifierarparametrarna är samma som parametrarna för samma namn som beskrivs för ODBC-datakällor. Se [ODBC-datakällor](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* Till skillnad från ODBC-datakällor kräver [!DNL ODBCLookup]-omformningar ingen ökande ID-kolumn. Se [ODBC-datakällor](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). Det beror på att innehållet i uppslagstabellen inte får ändras på något sätt medan datauppsättningen är aktiv. Det går inte att identifiera ändringar i en uppslagstabell eller vy förrän omformningen görs. Mer information om hur du ombearbetar data finns i [Återbearbetning och omformning](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

Anta att du vill konvertera inaktuella DNS-poster till uppdaterade poster. Båda uppsättningarna med poster lagras i en SQL-databas. Om du vill utföra den här åtgärden refererar du till en uppslagstabell som genereras från databasen och ersätter de inaktuella DNS-posterna.

I vårt exempel-transformering genomsöks loggposterna för s-dns-fältet, och om den finns används söktabellen VISUAL.LOOKUP för att jämföra s-dns-posten med posterna i kolumnen [!DNL OLDDNS] i tabellen. Om en rad finns i tabellen får utdatafältet s-dns den uppdaterade DNS-postposten från kolumnen [!DNL NEWDNS] i den identifierade raden.

![](assets/cfg_TransformationType_ODBCLookup.png)
