---
description: Frågesträngen (cs-uri-query) används ofta av webbprogram och webbplatsutvecklare för att skicka information från sida till sida på grund av HTTP-filens tillståndslösa karaktär.
solution: Analytics
title: Förstå frågesträngen
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Förstå frågesträngen{#understanding-the-query-string}

Frågesträngen (cs-uri-query) används ofta av webbprogram och webbplatsutvecklare för att skicka information från sida till sida på grund av HTTP-filens tillståndslösa karaktär.

I många fall kan information skickas i frågesträngen när den hämtas av [!DNL Sensor] webbservern. Sådan information kan användas av för [!DNL Site] att belysa webbplatsens verkliga struktur, besökarnas väg genom den samt annan information.

På vissa dynamiska webbplatser är name=value-par (variabler) i frågesträngen viktiga för att avgöra vilken sida som begärs av en besökare. I sådana fall kan URL-adresser struktureras på följande eller liknande sätt:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

I det här exemplet är PAGENAME i själva verket indikatorn för vilken sida som ska skickas till den som beställer den här URL:en. Många verktyg och tjänster för analys av webbloggar begränsar en webbplatsoperators möjlighet att definiera vad en sida finns på platsen baserat på vilka frågesträngsvariabler som finns i frågesträngarna i webbplatsens URL:er. Data Workbench-servern och data workbench kan konfigureras att använda sådana frågenamn för att definiera unika sidor. Detta är viktigt eftersom många system skulle tolka följande URL:er som samma sida, men [!DNL Site] inte det.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

På samma sätt lägger webbplatsutvecklare och program ofta till många frågesträngsvariabler i en webbplats URL:er som inte har något att göra med att identifiera den sida som begärs. Exempel visas nedan:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

I det här exemplet har frågesträngvariabeln CAMPAIGN= lagts till i URL:en. Den här CAMPAIGN-variabeln används för att ange vilken marknadsföringskampanj som fick en besökare att välja den här URL:en. [!DNL Site] kan konfigureras att använda den här CAMPAIGN-informationen, men separera den från definitionen av vilken sida en besökare visade så att du i din lista över sidor för rapporterings- och analysändamål bara kan se följande:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

