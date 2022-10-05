---
description: Sensorn hämtar alla mätdata som finns på sidförfrågningar (GET-förfrågningar) som görs till de webbservrar där den har installerats.
title: Hämtar data för sidbegäran
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 1%

---

# Hämtar data för sidbegäran{#acquiring-page-request-data}

{{eol}}

Sensorn hämtar alla mätdata som finns på sidförfrågningar (GET-förfrågningar) som görs till de webbservrar där den har installerats.

[!DNL Sensor] hämtar mätdata via webbserverns programmeringsgränssnitt, direkt från instansen eller instanserna av webbserverprogrammet som körs på webbservern. [!DNL Sensor] har inte åtkomst till webbservergenererade loggfiler. Faktum är, efter [!DNL Sensor] och data workbench-servern har installerats och testats kan webbserverns inbyggda loggningsfunktion inaktiveras utan att datainsamlingen påverkas. Om du inaktiverar loggning av filer till de lokala diskarna på själva webbserverdatorerna förbättras i många fall kapaciteten för sidbetjäning på dessa webbservrar eftersom det finns en ganska stor mängd fast disk-I/O som krävs för att logga informationen till den lokala disken på webbserverdatorn.

[!DNL Sensor] samlar in mätnings- och webbförfrågningsdata direkt från varje webbserverprocess och virtuell webbserverprocess (om tillämpligt) och skriver tillfälligt data till en köfil, en feltolerant minneskö med fast diskuppbackning, på webbserverdatorn. Tjänsten Sensor Transmitter (eller daemon beroende på plattform) hämtar data från köfilen och komprimerar och krypterar dem sedan innan de skickas till data workbench-servern för långtidslagring. Med [!DNL Sensor], samlas data bara in på webbserverdatorerna i köfilen om du har ett nätverk eller något annat problem som förhindrar att den skickas. Köfilen gör att det går att effektivt lagra timmar till dagar med webbförfrågningsdata för att skydda data om ett nätverks- eller systemfel inte tillåter att data överförs till Workbench-servern i realtid.

[!DNL Sensor] samlar in mätdata från varje fysisk och logisk webbserverprocess, filtrerar dem efter innehållstyp, komprimerar dem, krypterar dem och direktuppspelar dem till data workbench-servern.

Följande tabell innehåller fälten med logginformation som hämtas av [!DNL Sensor] för varje GET-begäran som inte filtreras bort baserat på [!DNL Sensor’s] konfigurationsfil:

<table id="table_5F65474150EC41648B35D0B031FB9B15">
 <thead>
  <tr>
   <th colname="col1" class="entry"> W3C-namn </th>
   <th colname="col2" class="entry"> Insamlade data </th>
   <th colname="col3" class="entry"> Förklaring </th>
   <th colname="col4" class="entry"> Förklaring </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> Spåra identifierare (unik besökare) </td>
   <td colname="col3"> Identifieraren läser från en cookie som placerats i användarens webbläsare av <span class="wintitle"> Sensor </span> på besökarens ursprungliga begäran </td>
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Datum </p> <p>Tid </p> </td>
   <td colname="col2"> Tidsstämpel </td>
   <td colname="col3"> Den tidpunkt då begäran bearbetades av servern (med 100 nanos precision; tillförlitligheten beror på servermiljön och NTP) </td>
   <td colname="col4"> 2002-11-21 17:21:45.123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> Innehållstyp </td>
   <td colname="col3"> Typ av objekt som returneras från servern </td>
   <td colname="col4"> text/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> Statuskod för HTTP-svar </td>
   <td colname="col3"> Numerisk kod som genereras av servern som antecknar status för HTTP-serverns svar </td>
   <td colname="col4"> 404 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-dator </td>
   <td colname="col2"> URI-stam </td>
   <td colname="col3"> Stamdelen av URI:n som begärts av klienten </td>
   <td colname="col4"> <span class="filepath"> pagedir/page.asp </span> </td>
  </tr>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> Klient-IP </td>
   <td colname="col3"> Den begärande klientens IP-adress </td>
   <td colname="col4"> 127.0.0.1 </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> Serverdomännamn </td>
   <td colname="col3"> Domännamn för webbservern som bearbetar begäran </td>
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(reference) </td>
   <td colname="col2"> Refererande URL </td>
   <td colname="col3"> Innehåll i HTTP-referensfältet som skickas av klienten </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> Användaragent </td>
   <td colname="col3"> Enhet som används för att göra en begäran till HTTP-servern </td>
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0; +Windows+NT+5.1) </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> Klientcookies från domän </td>
   <td colname="col3"> Innehåll i alla användarens cookies för webbplatsen </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> Frågesträng </td>
   <td colname="col3"> Eventuell frågesträngsdel av den URI som begärts av klienten </td>
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
