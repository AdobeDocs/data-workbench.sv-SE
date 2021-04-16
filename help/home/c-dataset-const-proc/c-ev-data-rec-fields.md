---
description: Information om de datafält som Data Workbench-servern kan bearbeta för att skapa en datauppsättning.
title: Fält för händelsedatapost
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
exl-id: 35433b87-991a-4fb9-ba6a-3217e89eb769
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 0%

---

# Händelsedatapostfält{#event-data-record-fields}

Information om de datafält som Data Workbench-servern kan bearbeta för att skapa en datauppsättning.

* [Om händelsedata](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [Fält för baslinjedatapost för händelser](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [Härledda fält](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## Om händelsedata {#section-3a0705f8c1824017aa4effed9903efbe}

Händelsedata som används för att skapa en datauppsättning finns i filer som kallas loggkällor. De data som är tillgängliga i loggkällorna kallas händelsedata eftersom varje datapost representerar en transaktionspost eller en enda instans av en händelse med en associerad tidsstämpel.

Händelsedata för en loggkälla samlas in i realtid av [!DNL Sensors]. Händelsedata som samlats in av [!DNL Sensors] från HTTP- och programservrar överförs till data workbench-servrar, som konverterar data till komprimerade loggfiler ( [!DNL .vsl]). Händelsedata som finns i en platt fil, XML-fil eller en ODBC-datakälla läses av data workbench-servern, som tillhandahåller avkodare som du definierar för att extrahera en gemensam uppsättning datafält från dessa olika format.

Följande avsnitt innehåller information om de datafält (kallas händelsedatafält eller loggpostfält) som samlas in av [!DNL Sensors] eller läses och görs tillgängliga för data workbench-servern.

>[!NOTE]
>
>Namnen på fälten följer vanligtvis namnkonventionen för det utökade loggfilformatet W3C. Många av fälten har prefix som anger källan till informationen i fältet:

* cs indikerar kommunikation från klienten till servern.
* sc anger kommunikation från servern till klienten.
* s anger information från servern.
* c anger information från klienten.
* x anger information som skapas av en Adobe-produkt.

## Fält för baslinjehändelsedatapost {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

Loggfiler ( [!DNL .vsl]) innehåller fält med händelsedata som samlas in från servrar av [!DNL Sensors] och används av data workbench-servern i datauppsättningsprocessen. I följande tabell visas fälten i en vanlig händelsedatapost som registrerats av [!DNL Sensor]:

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>Klientens IP-adress som den ingår i begäran till servern. </p> <p> Exempel: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>De cookies som klienten skickade med begäran. </p> <p> Exempel: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(reference) </td> 
   <td colname="col2"> <p>Den HTTP-referenssträng som klienten skickade till servern med begäran. </p> <p> Exempel: <span class="filepath"> http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>Strängen som klienten skickar med sin begäran till servern som anger vilken typ av användaragent klienten är. </p> <p> Exempel: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US, rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>Metodtypen för HTTP-begäran. </p> <p> Exempel: GET </p> <p> Referens: <span class="filepath"> http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>Frågesträngsdelen av URI (stam + frågesträng = URI). Detta föregås av ett frågetecken (?) och kan innehålla ett eller flera namn/värde-par avgränsade med et-tecken (&amp;). </p> <p> Exempel: page=hemsida </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-dator </td> 
   <td colname="col2"> <p>Stamdelen av URI (stam + frågesträng = URI). Stapeln är den faktiska eller logiska sökvägen till den begärda resursen på servern. </p> <p> Exempel: <span class="filepath"> /index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>Innehållstypen för resursen som begärs av klienten enligt rapporten från servern. </p> <p> Exempel: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>Antal byte data som har skickats från servern till klienten som svar på begäran </p> <p> Exempel: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>Statuskoden som servern returnerade till klienten. </p> <p> Exempel: 200 </p> <p> Referens: <span class="filepath"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>Det fullständiga kvalificerade domännamnet eller IP-adressen för värddatorn för den begärda resursen. </p> <p> Exempel: <span class="filepath"> www.adobe.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experiment </td> 
   <td colname="col2"> <p>Listan över alla kontrollerade experimentnamn och grupper som klienten är medlem i vid tidpunkten för begäran. </p> <p> Exempel: VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>Datum och tid (GMT) då begäran togs emot av servern. Tiden uttrycks som antalet 100 nanosekunder sedan 1 januari 1600. </p> <p> Exempel: 127710989320000000 är x-timestamp-värdet för 11:28:52.000000 på tisdagen den 13 september 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>64-bitars hexadecimalt värde för den unika webbläsaridentifieraren som finns i en beständig cookie som anges av en <span class="wintitle">-sensor </span> och som tillhandahålls av klienten med en begäran till en server. </p> <p> Exempel: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Härledda fält {#section-b6c57ee2aa31469fbd5dab90e52bc677}

Tabellen nedan innehåller exempel på fält som härleds av data workbench-servern från baslinjehändelsedatafälten:

<table id="table_3B008F1314804A69AE69E8F94908F497"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(cookie)(name) </td> 
   <td colname="col2"> Värdet för ett angivet namn/värde-par i en cookie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(reference-domain) </td> 
   <td colname="col2"> <p>Domännamnet eller IP-adressen för den refererande HTTP-URI:n. </p> <p> <p>Obs!  Det här fältet är skrivskyddat. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(reference-host) </td> 
   <td colname="col2"> <p>Skådarens hela värdnamn. </p> <p> Exempel: Om cs(reference) är <span class="filepath"> http://my.domain.com/my/page </span> är cs(reference-host) <span class="filepath"> my.domain.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(reference-query)(name) </td> 
   <td colname="col2"> <p>Värdet för en frågesträng för referent. </p> <p> <p>Obs!  Du kan inte komma åt ett frågesträngsvärde för en referent med hjälp av fältet cs(referrer)(name). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>Den fullständiga URI:n (stam + frågesträng = hela URI). </p> <p> Exempel: <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query(name) </td> 
   <td colname="col2"> <p>Värdet som är associerat med det angivna namnet. Om det finns flera värden för det angivna namnet returneras det sista av dessa värden. </p> Exempel: 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> För URI:n <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> returnerar cs-uri-query(product3) cd. </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> För URI:n <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span> returnerar <span class="wintitle"> cs-uri-query(product1) </span> casette. </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ctime </td> 
   <td colname="col2"> x-timestamp, uttryckt i sekunder sedan 1 januari 1970. Det här fältet kallas även x-unixtime. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> datum </td> 
   <td colname="col2"> x-timestamp i formatet YYYY-MM-DD. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> tid </td> 
   <td colname="col2"> x-timestamp i formatet HH:MM:SS. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-local-timestring </td> 
   <td colname="col2"> <p>x-timestamp konverteras till den lokala tidszonen som anges i filen <span class="filepath"> Transformation.cfg </span> för datauppsättningen. Formatet är YYY-MM-DD HH:MM:SS.mmm. </p> <p> <p>Obs!  Du kan också definiera tidskonverteringar som x-local-timestring i filen <span class="filepath"> Log Processing.cfg </span>. Mer information finns i <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Loggbearbetningskonfigurationsfil </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>Den identifierare som motsvarar loggkällan för en viss loggpost. För att identifieraren ska kunna registreras måste du ange den i fältet <span class="wintitle"> Loggkälla-ID </span> i filen <span class="filepath"> Log Processing.cfg </span> när du definierar <span class="wintitle"> sensor </span>, loggfil eller ODBC-datakällor. Mer information finns i <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Loggbearbetningskonfigurationsfil </a>. </p> <p> Exempel: från VSensor01. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> Maskmönstret för datakällorna <span class="wintitle"> sensor </span> (härleds från filnamnen <span class="filepath"> .vsl </span>). För en fil vars namn har formatet <span class="filepath"> YYYMMDD-SENSORID.VSL </span> är x-mask SENSORID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> x-timestamp i formatet YYYY-MM-DD HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> Den decimala UNIX-tiden som härleds från x-timestamp. </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Sensor]kan, när den används på en server, samla in fält med händelsedata från alla giltiga HTTP-begäranden, svarsrubriker eller variabler som är tillgängliga för den via serverns API. Om du vill samla in sådana datafält måste du ange önskade rubrikfält eller variabler i [!DNL txlogd.conf]konfigurationsfilen för [!DNL Sensor]. Mer information finns i *Datan Workbench [!DNL Sensor] Guide*.
