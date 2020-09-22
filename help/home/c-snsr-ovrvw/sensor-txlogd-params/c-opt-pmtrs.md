---
description: Information om valfria parametrar för filen txlogd.conf för sensorn.
solution: Analytics
title: Valfria parametrar
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 0%

---


# Valfria parametrar{#optional-parameters}

Information om valfria parametrar för filen txlogd.conf för sensorn.

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>Gör att du kan filtrera angivna IP-adresser. </p> <p>När du filtrerar en viss adress loggas inget "paket". Den här funktionen eliminerar interna eller övervakade agenter före loggbearbetning, vilket ökar hastigheten på loggbearbetningen och minskar behovet av datalagring. Du kan använda jokertecken när du anger adresser. </p> <p>Exempel: <span class="filepath"> AddressFilter 10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>InnehållsfilterInkludera </p> <p>InnehållsfilterUteslut </p> </td> 
   <td colname="col2"> <p>Ange om vissa typer av innehåll ska inkluderas eller exkluderas från loggning. </p> <p>Parametervärdena är prefix-matchade mot svarets innehållstyp. </p> <p>"image/" matchar till exempel alla bildinnehållstyper medan "image/gif" endast matchar den typen exakt. När det finns flera matchningar för en viss innehållstyp används den mest specifika matchningen. Därför kan du placera"image/gif" i parametern ContentFilterInclude och"image/" i parametern ContentFilterExclude och"image/gif"-svar tillåts, men alla andra bildtyper filtreras bort. </p> <p>Exempel: <span class="filepath"> ContentFilterInclude *</span> </p> <p>Exempel: <span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>Ange bara den här parametern när du arbetar med Adobe konsulttjänster. </p> <p>Aktiverar felsökningsloggning för webbmodulen och sändaren. </p> <p>Du använder den här parametern när <span class="wintitle"> sensorn</span> inte fungerar som den ska. När den här parametern har angetts måste du skapa en tom fil på den angivna sökvägen och ge skrivrättigheter till den för alla användare. (i ett unikt skal på webbservern): 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>Du bör endast aktivera felsökningsloggning under en kort tidsperiod, efter vilken loggfilen ska skickas till Adobe Consulting Services för analys. </p> <p>Exempel: <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe rekommenderar att den här parametern först ställs in i en testmiljö för att avgöra vilken effekt systemet har. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>Inaktiverar det angivna fältet </p> <p>Användarna kan ta bort fält som de inte använder eller inte vill lagra. Om fältet tar strängvärden skickas en tom sträng om du inaktiverar det. Om fältet har numeriska värden skickas talet noll (0) om du inaktiverar det. Du kan inaktivera följande fält: 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-dator </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(reference) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(content-type) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x-experiment </li> 
     </ul> </p> <p>Exempel: <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>Sökväg till konfigurationsfilen för kontrollerade experiment. </p> <p>Exempel: <span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>Resurs som, när den begärs, genererar ett nytt spårnings-ID och användaren placeras i en experimentgrupp. </p> <p> <p>Obs!  Den här resursen behöver inte finnas fysiskt på webbservern. </p> </p> <p>Exempel: <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>Om du vill att dina kontrollerade experiment ska kunna mappa hela platsen eller en hel underkatalog till en annan plats anger du den här parametern till "on". Standardvärdet är "off". </p> <p>Exempel: <span class="filepath"> ExpPartialMatch av</span> </p> <p> <p>Obs!  Var mycket försiktig när du ställer in den här parametern på "on". </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>Avgör om varje ny användares första klick loggas även om användaren begär en dokumenttyp som filtreras bort av parametern ContentFilterExclude. </p> <p>Standardvärdet är "no". </p> <p>Bildfiler filtreras vanligtvis bort med parametern ContentFilterExclude. Om LogAllNewUsers är inställd på"yes" och det första dokumentet som en ny användare får från servern är en bild, loggas denna begäran. Om parametern LogAllNewUsers antingen är inställd på "no" eller inte alls (och förutsatt att bilderna filtreras bort av parametern ContentFilterExclude) och det första dokumentet som en ny användare får från servern är en bild, loggas inte denna begäran. </p> <p>Exempel: <span class="filepath"> LogAllNewUsers no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>Den tid i sekunder som sändaren väntar på att skicka nästa grupp med paket. </p> <p>Standardvärdet är 15. </p> <p>Exempel: <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>Obs!  Ändra inte det här parametervärdet utan att först kontakta Adobe Consulting Services. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>Gör att du kan inaktivera besöksspårning, som kan användas för att följa avanmälningsprinciper. </p> <p>När det här alternativet är aktiverat loggar <span class="wintitle"> Sensor</span> inte något "paket" för någon besökare vars V1st-cookie är inställd på det angivna PrivacyID:t. Eftersom ingen information har loggats för besökarna skickas ingen information om besökarna till <span class="keyword"> data workbench-servern</span> för behandling. </p> <p>Om du vill aktivera den här funktionen måste du utföra följande steg: 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID måste definieras med värdet 0 (noll) i filen txlogd.conf <span class="filepath"> för</span> sensorn <span class="wintitle"></span>. <p>Exempel: <span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">Webbplatsägare måste skriva kod för att ange besökares (V1st) cookies så att cookie-ID-värdet matchar PrivacyID-värdet som är definierat som"<span class="filepath"> txlogd.conf</span>". </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>Plats dit sändaren (txlogd) regelbundet skickar begäranden för att se om webbplatsen fungerar som den ska. </p> <p>Observera att platsen anges i följande format, inte som en URL-adress: </p> <p>http,<i>serveradress,port/resurs</i> </p> <p>där <i>serverAddress</i> är servernamn eller IP-adress är <i>port</i> serverns HTTP-lyssningsport och <i>resurs</i> är den specifika resurs som ska begäras (kan innehålla en frågesträng). </p> <p>Du kan ange flera SiteTest-rader. </p> <p>Exempel: <span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>Obs!  Endast http stöds för närvarande. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>Namnet på cookie-uppsättningen i besökarens webbläsare. </p> <p>Standardvärdet är "v1st". </p> <p>Exempel: <span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>Anger om servern ska valideras mot parametern CertName </p> <p>Standardvärdet är "on". </p> <p>Exempel: <span class="filepath"> VerifyCertName on</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>Ange bara den här parametern när du arbetar med Adobe konsulttjänster. </p> <p>Anger IIS- <span class="wintitle"> sensorn</span> vilken av två möjliga loggningskopplingar som ska användas för att logga ett paket </p> <p>Använd den här parametern när IIS- <span class="wintitle"> sensorn</span> inte loggar paket korrekt. Den här parametern skulle anges till "off" om standardloggningkroken inte fungerade korrekt. Standardvärdet är "on". </p> <p>Exempel: <span class="filepath"> IISCaptureBytesSkickat den</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>Ange bara den här parametern när du arbetar med Adobe konsulttjänster. </p> <p>Anger <span class="wintitle"> sensorn</span> vilken av två möjliga "krokar" som ska användas för att ställa in v1st-cookien. </p> <p>Du använder den här parametern när IIS- <span class="wintitle"> sensorn</span> inte ställer in v1st-cookien korrekt. Den här parametern ställs in på "yes" om standardkroken inte ställer in v1st-cookien korrekt. Standardvärdet är "no". </p> <p>Exempel: <span class="filepath"> IISUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Som standard skickar <span class="wintitle"> Sensor</span> svarsrubriker för cachekontroll vid varje begäran. När funktionen för cachekontroll är aktiverad skickar <span class="wintitle"> Sensor</span> en Expires-rubrik med värdet Thu, 16:00:00 GMT 1994, till webbläsaren. </p> <p>Du kan ändra svarssträngarna efter behov genom att redigera följande två rader i filen txlogd.conf <span class="filepath"></span> : </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Exempel: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Om du vill inaktivera sändning av svarsrubriker för cachekontroll skriver du ett bindestreck för varje rad enligt nedan: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> I den här parametern.. </th> 
   <th colname="col2" class="entry"> Ange... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Ange bara den här parametern när du arbetar med Adobe konsulttjänster. </p> <p>Anger <span class="wintitle"> sensorn</span> vilken av två möjliga "krokar" som ska användas för att ställa in v1st-cookien. </p> <p>Du använder den här parametern när Apache <span class="wintitle"> Sensor</span> inte ställer in v1st-cookien korrekt. Den här parametern ställs in på "yes" om standardkroken inte ställer in v1st-cookien korrekt. Standardvärdet är "no". </p> <p>Exempel: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUsebothHandlers </td> 
   <td colname="col2"> <p>Ange bara den här parametern när du arbetar med Adobe konsulttjänster. </p> <p>Instruerar <span class="wintitle"> sensorn</span> att försöka ställa in v1st-cookien i båda krokarna. </p> <p>Du använder den här parametern när Apache <span class="wintitle"> Sensor</span> inte ställer in v1st-cookien korrekt. Standardvärdet är"ja". </p> <p>Om värdet är ja och v1st-cookien inte är korrekt inställd i den första kroken används den andra kroken. Om värdet är "no" skulle du ställa in parametern ApacheUseAlternateHandler så att den anger vilken krok som ska användas för att ställa in v1st-cookien. </p> <p>Exempel: <span class="filepath"> ApacheUsebothHandlers - ja</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>Som standard skickar <span class="wintitle"> Sensor</span> svarsrubriker för cachekontroll vid varje begäran. När funktionen för cachekontroll är aktiverad skickar <span class="wintitle"> Sensor</span> en Expires-rubrik med värdet Thu, 16:00:00 GMT 1994, till webbläsaren. </p> <p>Du kan ändra svarssträngarna efter behov genom att redigera följande två rader i filen txlogd.conf <span class="filepath"></span> : </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Exempel: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>Om du vill inaktivera sändning av svarsrubriker för cachekontroll skriver du ett bindestreck för varje rad enligt nedan: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>Obs!  Adobe rekommenderar att du inte inaktiverar den här funktionen. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> I den här parametern.. </th> 
   <th colname="col2" class="entry"> Ange... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Ange bara den här parametern när du arbetar med Adobe konsulttjänster. </p> <p>Anger <span class="wintitle"> sensorn</span> vilken av två möjliga "krokar" som ska användas för att ställa in v1st-cookien. </p> <p>Du använder den här parametern när Apache <span class="wintitle"> Sensor</span> inte ställer in v1st-cookien korrekt. Den här parametern ställs in på "yes" om standardkroken inte ställer in v1st-cookien korrekt. Standardvärdet är "no". </p> <p>Exempel: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUsebothHandlers </td> 
   <td colname="col2"> <p>Ange bara den här parametern när du arbetar med Adobe konsulttjänster. </p> <p>Instruerar <span class="wintitle"> sensorn</span> att försöka ställa in v1st-cookien i båda krokarna. </p> <p>Du använder den här parametern när Apache <span class="wintitle"> Sensor</span> inte ställer in v1st-cookien korrekt. Standardvärdet är"ja". </p> <p>Om värdet är ja och v1st-cookien inte är korrekt inställd i den första kroken används den andra kroken. Om värdet är "no" skulle du ställa in parametern ApacheUseAlternateHandler så att den anger vilken krok som ska användas för att ställa in v1st-cookien. </p> <p>Exempel: <span class="filepath"> ApacheUsebothHandlers - ja</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

