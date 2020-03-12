---
description: Frågesträngsvariabler kan läggas till i en JavaScript-begäran för att samla in ytterligare mått när en begäran görs.
solution: Analytics
title: Hämta ytterligare information
topic: Data workbench
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hämta ytterligare information{#acquiring-additional-information}

Frågesträngsvariabler kan läggas till i en JavaScript-begäran för att samla in ytterligare mått när en begäran görs.

Dessa variabler kan läggas till manuellt eller av skript på själva sidan.

Ytterligare information som kan hämtas från en sida kan läggas till i det inbäddade objektet via skript med följande kod som exempel:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
v["_1"] = “99.99”; 
v["_2"] = "visa"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
<noscript> 
 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
<!-- END REFERENCE PAGE TAG-->
```

I det här exemplet kan skriptvariablerna för v_1 och v_2 härledas från en annan funktion på webbsidan. Variablerna har infogats som exempel. Förutom de baslinjemått som erhållits vid varje begäran, skulle följande utökade mått erhållas med begäran av URL:en ovan:

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_pn= | Värde som är associerat med v_pn-frågesträngsvariabeln | v_pn=Ansökningsformulär |
| v_1= | Värde som är associerat med frågesträngsvariabeln v_1 | v_1=99.99 |
| v_2= | Värde som är associerat med variabeln v_2-frågesträng | v_2=visa |
