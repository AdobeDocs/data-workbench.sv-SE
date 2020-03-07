---
description: Samla in aktivitet över webbplatslänkar från tredje part för att aktivera analys av slutmål.
solution: Analytics
title: Spåra avslut till externa länkar
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Spåra avslut till externa länkar{#tracking-exits-to-external-links}

Samla in aktivitet över webbplatslänkar från tredje part för att aktivera analys av slutmål.

Webbsidor kan innehålla länkar till tredjepartswebbplatser, och aktivitet över dessa länkar kan samlas in för att aktivera analys av slutmål, särskilt om tredjepartswebbplatsen ansvarar för att betala hänvisningsavgifter när sådana hänvisningar tas emot. Eftersom klickningshändelsen som standard skrivs till loggfilerna för tredjepartssystemet måste länken ändras för att klickhändelsen ska kunna hämtas lokalt. Tredjepartslänken som finns på webbplatsen måste ändras på följande sätt:

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

Den refererade [!DNL PageExit.htm] filen måste skapas och ska struktureras så att den innehåller följande skript:

```
<html> 
<head> 
 
<script> 
function getExitURLQuery(variable) 
{ 
 
var query = window.location.search.substring(1); 
var vars = query.split("&"); 
for (var i=0; i<vars.length; i++) 
{ 
var pair = vars[i].split("="); 
if (pair[0] == variable) 
{ 
return pair[1]; 
} 
 }  
} 
</script> 
 
<script> 
location.replace(getExitURLQuery("v_eurl")); 
</script>  
 
</head> 
</html>
```

Genom att begära filen [!DNL PageExit.htm] samlas v_eurl-värdet in i analyssyfte. När [!DNL PageExit.htm] den läses in dirigeras den dessutom omedelbart om till den angivna v_eurl-målplatsen.

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_eurl | Värdet som är associerat med strängvariabeln v_eurl. Det här värdet representerar mål-URL:en för länken som finns på HTML-sidan. | v_eurl=www.othersite.com |
