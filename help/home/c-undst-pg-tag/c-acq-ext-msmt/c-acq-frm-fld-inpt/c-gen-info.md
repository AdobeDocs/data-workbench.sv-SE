---
description: Värden som anges i ett formulär på en webbsida kan samlas in och läggas till i frågesträngen på den efterfrågade sidan (när formuläret skickas) med hjälp av JavaScript.
solution: Analytics
title: Allmän information
topic: Data workbench
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Allmän information{#general-information}

Värden som anges i ett formulär på en webbsida kan samlas in och läggas till i frågesträngen på den efterfrågade sidan (när formuläret skickas) med hjälp av JavaScript.

Detta visas i följande exempel. Inkludera detta JavaScript efter alla formulärvalideringsskript som används på HTML-sidorna.

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

I det här exemplet läggs värdena som anges i formuläret av webbläsaranvändaren till den efterföljande&quot;thankyou.asp&quot;-sidan som anges i värdet för FORM-åtgärd enligt följande:

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

Följande utökade mått skulle erhållas med denna begäran, utöver de basmått som samlats in av [!DNL Sensor]:

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_1 | Värde som är associerat med formulärfältet NAME | v_1=Sven Svensson |
| v_2 | Värde som är associerat med formulärfältet CITY | v_2=Los Angeles |
| v_3 | Värde som är associerat med STAT-formulärfältet | v_3=Kalifornien |
| v_4 | Värdet som är associerat med ZIP-formulärfältet | v_4=90210 |

