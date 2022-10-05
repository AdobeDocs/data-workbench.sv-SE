---
description: Frågesträngen (cs-uri-query) används ofta av webbprogram och webbplatsutvecklare för att skicka information från sida till sida på grund av HTTP-filens tillståndslösa karaktär.
title: Förstå frågesträngen
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Förstå frågesträngen{#understanding-the-query-string}

{{eol}}

Frågesträngen (cs-uri-query) används ofta av webbprogram och webbplatsutvecklare för att skicka information från sida till sida på grund av HTTP-filens tillståndslösa karaktär.

I många fall kan information skickas i frågesträngen när den hämtas av [!DNL Sensor] på webbservern. Sådan information kan användas av [!DNL Site] för att belysa webbplatsens verkliga struktur, besökarnas väg genom den samt annan information.

På vissa dynamiska webbplatser är name=value-par (variabler) i frågesträngen viktiga för att avgöra vilken sida som begärs av en besökare. I sådana fall kan URL-adresser struktureras på följande eller liknande sätt:

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

I det här exemplet är PAGENAME i själva verket indikatorn för vilken sida som ska skickas till den som beställer den här URL:en. Många verktyg och tjänster för analys av webbloggar begränsar en webbplatsoperators möjlighet att definiera vad en sida finns på platsen baserat på vilka frågesträngsvariabler som finns i frågesträngarna i webbplatsens URL:er. Data Workbench-servern och data workbench kan konfigureras att använda sådana frågenamn för att definiera unika sidor. Detta är viktigt eftersom många system skulle tolka följande URL:er som samma sida, men [!DNL Site] inte.

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
https://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

På samma sätt lägger webbplatsutvecklare och program ofta till många frågesträngsvariabler i en webbplats URL:er som inte har något att göra med att identifiera den sida som begärs. Exempel visas nedan:

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

I det här exemplet har frågesträngvariabeln CAMPAIGN= lagts till i URL:en. Den här CAMPAIGN-variabeln används för att ange vilken marknadsföringskampanj som fick en besökare att välja den här URL:en. [!DNL Site] kan konfigureras att använda den här CAMPAIGN-informationen, men separera den från definitionen av vilken sida en besökare visade så att du i din lista över sidor för rapporterings- och analysändamål bara kan se följande:

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
