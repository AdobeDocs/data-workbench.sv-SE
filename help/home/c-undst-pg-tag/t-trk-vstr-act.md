---
description: Webbplatser som byggts med Flash kräver särskild uppmärksamhet när det gäller att fånga besökaraktiviteter som utförts i multimediematerialet.
title: Spåra besöksaktivitet i Flash multimediematerial
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 2%

---

# Spåra besöksaktivitet i Flash multimediematerial{#tracking-visitor-activity-within-flash-rich-media-content}

Webbplatser som byggts med Flash kräver särskild uppmärksamhet när det gäller att fånga besökaraktiviteter som utförts i multimediematerialet.

Med [!DNL Flash] ActionScript kan du göra enkla ändringar i dina befintliga [!DNL Flash]-filmer för att tillåta spårning av alla besökares interaktioner med filmen, till exempel knappklickningar eller musrörelser.

Följ stegen nedan för att underlätta aktivitetsspårning för besökare i din [!DNL Flash]-film:

1. Lägg till följande ActionScript-kod i filmen. Den här koden representerar en funktion som kan anropas av händelser i den [!DNL Flash]-film som du vill spåra.

   ```
   // FLASH TAG CODE BEGIN
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt";
   function tag(PAGENAME,VARIABLES) {
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0);
   }
   // FLASH TAG CODE END
   ```

1. Skapa en tom fil med namnet [!DNL flashtag.txt] och placera filen på dina webbservrar.
1. Ersätt platshållaren \[[!DNL PATH_TO_WEB_SERVER]\] i funktionen i steg 1 med den fullständiga eller relativa sökvägen till platsen för filen [!DNL flashtag.txt]. Exempel:

   ```
   var FLASHTAGURI = https://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Lägg till följande ActionScript-kod i alla händelser som ska spåras. Den här koden representerar ett funktionsanrop som används för att samla in data om händelsen:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   I det här exemplet visas hur händelsen on(release) används. Funktionen tag() kan emellertid refereras via alla händelser som du vill spåra, till exempel en on(press)-, on(rollover)-, on(rollout)- eller on(keypress)-händelse.

   Platshållaren \[[!DNL PUT_PAGE_NAME_HERE]\] bör ersättas med en sträng som representerar namnet på sidan eller händelsen som du spårar. Variabeln \[[!DNL PUT_PAGE_NAME_HERE]\]kan ändras antingen manuellt eller via variabelreferens för att ange ett unikt namn för sidan eller händelsen i [!DNL Flash]-programmet. Värdet som ersätter platshållaren \[[!DNL PUT_PAGE_NAME_HERE]\] kan bestå av ett enkelt namn eller vara strukturerat för att representera en hierarkisk struktur som liknar en fullständig URI. Exempel:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe rekommenderar att du innan du driftsätter kod sammanställer en skriftlig specifikation för sidnamn och händelsenamn för att underlätta anpassningen av affärskrav och utvecklingsuppgifter och minska risken för ytterligare utvecklingscykler.

1. Om du vill kan ytterligare variabler samlas in och associeras med sidor eller händelser i [!DNL Flash]-filmen. Om du vill göra det ersätter du platshållaren \[[!DNL PUT_ADDITIONAL_VAR_HERE]\] med en uppsättning namn=value-par avgränsade med ett et-tecken (&amp;). Exempel:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   Variablerna kan ändras antingen manuellt eller via variabelreferenser för att ange ytterligare attribut som ska samlas in och kopplas till sidan eller händelsen. Om det inte finns några tillämpliga ytterligare variabler att samla in tar du bort \[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   Din inställning av besöksspårning i [!DNL Flash] multimediematerial är nu klar. När händelsen anropas anropas taggen [!DNL (PAGENAME,VARIABLES)]-funktionen, vilket resulterar i en HTTP-begäran för följande fil. Den här funktionen anropas förutom andra funktioner som kan aktiveras enligt definitionen i din [!DNL Flash]-film:

   ```
   https://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

HTTP-begäran som är ett resultat av funktionen [!DNL Flash] Tagg ActionScript resulterar i att följande information samlas in för varje händelse i [!DNL Flash]-filmen. Den sista raden i tabellen (W3C Name cs-uri-query) representerar information som samlats in för de ytterligare variabler som anges i funktionsanropet.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4">
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
   <td colname="col3"> Identifieraren läste från en cookie som placerats i användarens webbläsare av <span class="wintitle"> sensor </span> på besökarens ursprungliga begäran </td>
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td>
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
   <td colname="col4"> Text/html </td>
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
   <td colname="col3"> Stamdelen av URI:n som begärts av klienten </td>
   <td colname="col4"> /flashtag/flashtag.txt </td>
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
   <td colname="col4"> www.mysite.com </td>
  </tr>
  <tr>
   <td colname="col1"> cs(reference) </td>
   <td colname="col2"> Refererande URL </td>
   <td colname="col3"> Innehåll i HTTP-referensfältet som skickas av klienten </td>
   <td colname="col4"></td>
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
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td>
  </tr>
 </tbody>
</table>
