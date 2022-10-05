---
description: Webbsidor är ofta strukturerade med programmeringsspråket ASP (Active Server Pages).
title: ASP-specifik information
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# ASP-specifik information{#asp-specific-information}

{{eol}}

Webbsidor är ofta strukturerade med programmeringsspråket ASP (Active Server Pages).

ASP är en Microsoft-teknik som körs i IIS (Internet Information Services). När en webbläsare begär en ASP-fil skickar IIS begäran till ASP-motorn. ASP-motorn läser ASP-filen, rad för rad, och kör skripten i filen. Slutligen returneras ASP-filen till webbläsaren som HTML. ASP tillhandahåller RESPOND- eller REQUEST-objekt som, utöver andra användningsområden, tillåter svar eller begäran från användarfrågor eller data som skickas från HTML-formulär.

I vissa fall kanske du inte vill lägga till de värden som anges i formulären till den URL som visas i adressfältet i en användares webbläsare eller som kan visas i själva HTML-koden. Med enkel JavaScript på serversidan kan du lägga till formulärfältsnamn och deras respektive värden i loggfilen utan att göra dem tillgängliga i användarens webbläsare eller bädda in dem i HTML-filen. Om du vill hämta in de faktiska formulärvärdena som anges i vissa formulär på webbplatsen måste du lägga till några kodrader för att lägga till formulärvärdena i loggbegäran.

Inkludera följande kod på en formulärs bearbetningssida för att lägga till de angivna formulärvärdena i data som efterfrågas (utöver att skriva de skickade formulärvärdena till en extern databas eller annan plats):

```
var sName= Request.Form("Name");
var sCity= Request.Form("City");
var sState= Request.Form("State");
var sZip= Request.Form("Zip");

Response.AppendToLog("&v_1=" +  sName);
Response.AppendToLog("&v_2=" +  sCity);
Response.AppendToLog("&v_3=" +  sState);
Response.AppendToLog("&v_4=" +  sZip);
```

Den här processen lägger till formulärvärdena enligt definitionen i begärandedata för [!DNL Form Processing] sida. I loggdata är de tillagda värdena tillgängliga som frågesträngar för [!DNL Form Processing] sida enligt nedan. v_1, v_2, v_3 och v_4 skulle nu vara frågesträngar som innehåller data som anges i rätt formulärfält. Syntaxen som beskrivs i exemplet ovan kan dupliceras för alla ytterligare formulärfält och värden som du vill hämta.

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Om du vill att alla formulärfält och värden ska hämtas och vara tillgängliga för analys kan du använda följande syntax:

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

I det här exemplet används alla formulärfält som finns i HTML tillsammans med deras respektive värden och de läggs till som frågesträngar i loggposten för [!DNL Form Processing] sida. Observera att detta inkluderar alla dolda fält i formuläret.

Loggdata ska utökas enligt följande tabell:

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_1 | Värde som är associerat med frågesträngen NAME | v_1=Sven Svensson |
| v_2 | Värde som är associerat med CITY-frågesträngen | v_2=Los Angeles |
| v_3 | Värde som är associerat med STATE-frågesträngen | v_3=Kalifornien |
| v_4 | Värde som är associerat med ZIP-frågesträngen | v_4=90210 |
