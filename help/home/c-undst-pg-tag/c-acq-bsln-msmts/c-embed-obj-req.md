---
description: När en sidas HTML-kod har begärts av en webbläsare begär webbläsaren att de inbäddade objekten som sidans HTML-kod refererar till ska fylla i sidan som visas av webbläsaren.
solution: Analytics
title: Hämta inbäddade objektbegäranden (sidtaggar)
topic: Data workbench
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 1%

---


# Hämta inbäddade objektbegäranden (sidtaggar){#acquiring-embedded-object-requests-page-tags}

När en sidas HTML-kod har begärts av en webbläsare begär webbläsaren att de inbäddade objekten som sidans HTML-kod refererar till ska fylla i sidan som visas av webbläsaren.

Sådana förfrågningar om inbäddade objekt är oftast förfrågningar om bildfiler eller JavaScript-filer, även om det finns hundratals eller kanske tusentals typer av inbäddade objekt som används på Internet idag. Många av dessa förfrågningar om inbäddade objekt är i allmänhet inte användbara vid analys eller rapportering av en webbplats affärsverksamhet. Många sådana förfrågningar är därför inte lämpliga för förvärv såvida de inte har ett specifikt affärssyfte, som att presentera en annons eller göra ett annat mått på webbplatsaktiviteten.

En bild kan till exempel vara en annons, och du kanske vill veta att annonsen imponerades av en besökare. Ett JavaScript-kodfragment kan användas för att göra en mätning av att webbläsaren har en viss egenskap och skicka tillbaka det till en [!DNL Sensor] för förvärv. Varje sida på en plats kan innehålla 10 eller 100 inbäddade objektbegäranden. Om en plats lagrar logginformation för varje begäran, multipliceras mängden data som behövs för att hålla loggdata tillgängliga för framtida analys med antalet inbäddade objektbegäranden för varje begärd sida. Därför [!DNL Site] kan du behålla de förfrågningar som är viktiga för analys och ignorera andra innan du ådrar dig onödiga lagringskostnader.

Genom att använda åsidosättningsfunktionen som finns i filtreringsfunktionerna för innehållstyp i [!DNL Sensor] (bifogar &quot;Log=1&quot; till frågesträngen för en inbäddad objektbegäran-URL) kan den aktuella inbäddade objektbegäran och relaterade mätdata hämtas utan att webbplatshanteraren behöver lagra alla begäranden av den typen (till exempel alla `<image>` begäranden).

[!DNL Sensor] samlar in mätdata i följande tabell för varje inbäddad objektbegäran som görs av webbservern, förutsatt att [!DNL Sensor] inte har konfigurerats för att filtrera ut eller att filtret har åsidosatts. Den insamlade informationen är relaterad till besökaren och sessionen och efterföljande sessioner via loggposterna x-trackingid eller cs(cookie).

<table id="table_11BE08A798E743EC8E76F738F0CE5884"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> W3C-namn </th> 
   <th colname="col2" class="entry"> Insamlade data </th> 
   <th colname="col3" class="entry"> Förklaring </th> 
   <th colname="col4" class="entry"> Exempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Spåra identifierare (unik besökare) </td> 
   <td colname="col3"> Identifieraren läser från en cookie som placerats i användarens webbläsare av <span class="wintitle"> Sensor </span> vid den första begäran </td> 
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
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-dator </td> 
   <td colname="col2"> URI-stam </td> 
   <td colname="col3"> Delen "stam" i URI:n som begärts av klienten </td> 
   <td colname="col4"> pagedir/page.asp </td> 
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
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> Användaragent </td> 
   <td colname="col3"> Enhet som används för att göra en begäran till HTTP-servern </td> 
   <td colname="col4"> <p>Mozilla/4.0+(compatible;+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Klientcookies från domän </td> 
   <td colname="col3"> Innehåll i alla användarens cookies för webbplatsen </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Frågesträng </td> 
   <td colname="col3"> Eventuell frågesträngsdel av den URI som begärts av klienten </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

