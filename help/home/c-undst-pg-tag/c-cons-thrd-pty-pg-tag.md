---
description: Konceptuell information om taggning från tredje part och förhindrande av cookie-blockering med P3P.
solution: Analytics
title: P3P-överväganden för sidtaggning från tredje part
topic: Data workbench
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# P3P-överväganden för sidtaggning från tredje part{#p-p-considerations-for-third-party-page-tagging}

Konceptuell information om taggning från tredje part och förhindrande av cookie-blockering med P3P.

## Om sidtaggning från tredje part {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

I de flesta implementeringar betraktas Adobes beständiga cookie som en cookie från första part. Första parts cookies definieras som cookies som är associerade med värddomänen.

Anta att en användare besöker http://www.example.com/. Om en sensor är installerad och fungerar på den webbserver som är värd för domänen anges en beständig cookie från Adobe och visas som en cookie från första part. Du kanske vill samla in mätdata från en tredjepartswebbplats med hjälp av inbäddade objekt, som begärs och läses in från servern som körs i stället [!DNL Sensor] för från tredjepartsservern som är värd för sidan eller annonsprogrammet. Till exempel visar http://www.example2.com/ en webbsida med en inbäddad objektbegäran från http://www.example.com/. Begäran om det inbäddade objektet från http://www.example.com/ leder till att en cookie ställs in. I detta sammanhang ser webbläsaren eller användaragenten cookien som en cookie från tredje part.

I nyare webbläsare som Microsoft IE6 filtrerar sekretessfunktioner cookies baserat på deras kompakta principer som skickas i HTTP-svarshuvudet från webbservern. I standardinställningarna för IE6, som de flesta användare aldrig ändrar, blockeras cookies från tredje part när de har obefintliga eller otillräckliga komprimerade principer. De flesta webbplatser som har problem med att blockera cookies har cookies från tredje part på sin webbplats som inte har rätt kompakta principer skickade i HTTP-svarshuvudet. Dessutom kan vissa problem med cookie-blockering uppstå när en webbplats ramas in av en annan plats. En onlinebutik som ingår i en onlinebutik kan till exempel visas i en ram från portalen. Ur webbläsarens perspektiv kan butiksinnehållet verka vara tredjepartsinnehåll när det ramas in av portalen. Men om en besökare går direkt till onlinebutiken utan att gå via portalen blir innehållet förstahandsinnehåll. Onlinebutiken hittar därför sina cookies bara när besökarna kommer in via portalen.

Webbaserade e-postsystem orsakar ett liknande problem. Om en webbplatsbesökare skickar en webbsida med e-post till en vän som använder ett webbaserat e-postsystem, visas e-postmeddelandet som tredjepartsinnehåll till vännens webbläsare eftersom det ramas in av e-postsystemet. Om det finns cookies associerade med sidan som e-postades behandlas de som cookies från tredje part av IE6.

## Använda P3P för att förhindra cookie-blockering {#section-96831cad887649f295aec6931750e41a}

P3P är ett standardsätt för webbplatser att koda sina integritetspolicyer i ett datorläsbart XML-format. P3P-aktiverade webbläsare och andra P3P-användaragenter hämtar automatiskt P3P-sekretesspolicyer, tolkar dem och jämför dem med användarens sekretessinställningar.

För att förhindra att IE6 blockerar cookies på din webbplats måste du se till följande:

1. Alla cookies som anges i en tredjepartskontext har P3P-kompakta profiler kopplade till sig.
1. Lämplig kompakt princip skickas med en anpassad HTTP-svarshuvud.
1. Dessa kompakta policyer anses tillfredsställande av IE6.
1. Om cookies från tredje part anges av ett annat företag kan du behöva be dem att aktivera P3P och ange P3P-kompakta profiler. Alla värdar som anger en P3P-kompakt princip måste också ha en motsvarande fullständig P3P-princip. Användare kan ändra sina IE6-inställningar så att cookies blockeras även under andra förhållanden. Om du placerar tillräckligt kompakta principer på cookies från tredje part förhindras dock de flesta cookie-blockeringar i IE6.

Följande är ett exempel på en sådan P3P-rubrik:

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

I det här exemplet [!DNL p3p.xml] används filen för att referera till en associerad [!DNL policy.xml] fil som finns på din webbserver och som anger vilken typ av information din webbplats samlar in, vilka tvistlösningsmetoder din organisation följer, hur insamlade data används, vem som äger data och annan standardinformation som rör integritet på Internet. De tre teckenkoderna efter &quot;CP&quot; är de kompakta policykoderna som emulerar det som anges i din [!DNL policy.xml] fil.

Alla kompakta policyer och XML-filer för policyer ska skräddarsys för respektive organisation som de ska distribueras till, och deras interna integritetspolicyer för insamling av webbplatsdata ska anges korrekt. En mängd redigerare för P3P-principer finns online tillsammans med mer detaljerad information om hur man implementerar en lämplig sekretesspolicy på webbplatsen.

Mer information om hur Internet Explorer 6 hanterar P3P-rubriker finns på:

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
