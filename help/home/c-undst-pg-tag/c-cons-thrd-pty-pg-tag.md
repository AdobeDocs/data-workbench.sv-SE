---
description: Konceptuell information om taggning från tredje part och förhindrande av cookie-blockering med P3P.
title: P3P-överväganden för sidtaggning från tredje part
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---

# P3P-överväganden för tredjeparts sidtaggning{#p-p-considerations-for-third-party-page-tagging}

Konceptuell information om taggning från tredje part och förhindrande av cookie-blockering med P3P.

## Om tredjepartssidtaggning {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

I de flesta implementeringar betraktas den beständiga cookien för Adobe som en cookie från en annan leverantör. Första parts cookies definieras som cookies som är associerade med värddomänen.

Anta att en användare besöker http://www.example.com/. Förutsatt att en sensor är installerad och i drift på webbservern som är värd för domänen, ställs en beständig cookie för Adobe in och visas som en cookie för första part. Du kanske vill samla in mätdata från en tredjepartswebbplats med hjälp av inbäddade objekt, som begärs och läses in från servern som kör [!DNL Sensor] i stället för från den tredjepartsserver som är värd för sidan eller annonsprogrammet. Till exempel visar http://www.example2.com/ en webbsida med en inbäddad objektbegäran från http://www.example.com/. Begäran om det inbäddade objektet från http://www.example.com/ leder till att en cookie ställs in. I detta sammanhang ser webbläsaren eller användaragenten cookien som en cookie från tredje part.

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

I det här exemplet används filen [!DNL p3p.xml] för att referera till en associerad [!DNL policy.xml]-fil som finns på din webbserver och som anger vilken typ av information som din webbplats samlar in, tvistlösningsmetoder som din organisation följer, hur insamlade data används, vem som äger data och annan standardinformation relaterad till Internet-sekretess. De tre teckenkoderna efter &quot;CP&quot; är de kompakta principkoderna som emulerar det som anges i [!DNL policy.xml]-filen.

Alla kompakta policyer och XML-filer för policyer ska skräddarsys för respektive organisation som de ska distribueras till, och deras interna integritetspolicyer för insamling av webbplatsdata ska anges korrekt. En mängd redigerare för P3P-principer finns online tillsammans med mer detaljerad information om hur man implementerar en lämplig sekretesspolicy på webbplatsen.

Mer information om hur Internet Explorer 6 hanterar P3P-rubriker finns på:

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
