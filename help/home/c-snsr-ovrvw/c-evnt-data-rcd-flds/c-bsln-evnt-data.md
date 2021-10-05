---
description: Information om baslinjehändelsedatapostfält som registrerats av sensorn.
title: Fält för baslinjedatapost för händelser
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
exl-id: ad3d8806-863a-4871-a35b-6680163f00ac
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# Fält för baslinjedatapost för händelser{#baseline-event-data-record-fields}

Information om baslinjehändelsedatapostfält som registrerats av sensorn.

<table id="table_E29606BB010E4DB48C463979B7BEC769">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Fält </th>
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> <p>Klientens IP-adress som den ingår i begäran till servern. </p> <p>Exempel: 207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>De cookies som klienten skickade med begäran. </p> <p>Exempel: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(reference) </td>
   <td colname="col2"> <p>Den HTTP-referenssträng som klienten skickade till servern med begäran. </p> <p>Exempel: https://www.mysite.net/cgi-bin/websearch?qry </p> <p>Om du använder sidtaggar är cs(referrer) den fullständiga URL:en för dokumentet som innehåller taggbilden, inklusive HTTP eller HTTP. </p> <p>Du kan också konfigurera Apache (1.3, 2.0 och 2.2) och IIS-sensorer så att de fångar den port som används för begäran, vilket kan identifiera HTTP- eller HTTPS-begäranden. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>Strängen som klienten skickar med sin begäran till servern som anger vilken typ av användaragent klienten är. </p> <p>Exempel: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US, rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>Metodtypen för HTTP-begäran </p> <p>Exempel: GET </p> <p>Referens: https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>Frågesträngsdelen av URI (rem + frågesträng = URI) </p> <p>Detta föregås av ett frågetecken (?) och kan innehålla ett eller flera namn/värde-par avgränsade med et-tecken (&amp;). </p> <p>Exempel: page=hemsida </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-dator </td>
   <td colname="col2"> <p>Stamdelen av URI (stam + frågesträng = URI) </p> <p>Stapeln är den faktiska eller logiska sökvägen till den begärda resursen på servern. </p> <p>Exempel: /index.asp </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> <p>Innehållstypen för resursen som begärs av klienten enligt rapporten från servern. </p> <p>Exempel: text/html, image/png, image/gif, video/mpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-bytes </td>
   <td colname="col2"> <p>Antalet byte med data som skickas från servern till klienten som svar på begäran. </p> <p>Exempel: 4996 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> <p>Statuskoden som servern returnerade till klienten. </p> <p>Exempel: 200 </p> <p>Referens: https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>Det fullständiga kvalificerade domännamnet eller IP-adressen för värddatorn för den begärda resursen. </p> <p>Exempel: www.omniture.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-experiment </td>
   <td colname="col2"> <p>Listan över alla kontrollerade experimentnamn och grupper som klienten är medlem i vid tidpunkten för begäran. </p> <p>Exempel: Home_exp.group_1,Registration_exp.group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>Datum och tid (GMT) då begäran togs emot av servern. </p> <p>Tiden uttrycks som antalet 100 nanosekunder sedan 1 januari 1600. </p> <p>Exempel: 127710989320000000 skulle vara x-timestamp-värdet för 11:28:52.000000 på tisdagen den 13 september 2005. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>64-bitars hexadecimalt värde för den unika webbläsaridentifieraren som finns i en beständig cookie som anges av en <span class="wintitle">-sensor </span> och som tillhandahålls av klienten med en begäran till en server. </p> <p>Exempel: 42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

[!DNL data workbench server] kan härleda ett antal variabler från baslinjehändelsedatafälten. Mer information finns i *Konfigurationshandboken för datauppsättningar*.
