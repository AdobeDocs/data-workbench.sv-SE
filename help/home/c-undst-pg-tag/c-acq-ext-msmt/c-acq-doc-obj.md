---
description: Med JavaScript Document Object Model kan ytterligare skriptmetoder användas för att förstärka begäran om zig.js-filen.
title: Hämta dokumentobjekt
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Hämta dokumentobjekt{#acquiring-document-objects}

Med JavaScript Document Object Model kan ytterligare skriptmetoder användas för att förstärka begäran om zig.js-filen.

Information som värdet på META-taggar, ID-värden för DIV-taggar och så vidare, kan refereras efter namn och samlas in som variabler för användning i analysen. Om du till exempel vill hämta information dynamiskt i META-elementet i HTML-dokumentet kan du använda följande JavaScript-syntax:

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_1"] = metacontent;
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_1= | Värdet som är associerat med frågesträngsvariabeln METAVALUE. Detta värde representerar data i META-elementet i HTML-dokumentet. | v_1=Den här sidan visar innehåll relaterat till sidan Beställningstack. |

När data har samlats in kan du konfigurera data workbench-servern så att den bearbetar mätdata för analys och rapportering.
