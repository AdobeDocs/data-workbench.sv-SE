---
description: Taggen för referenssidan består av ett körningsskript för sidtaggar som finns på en webbserver, och när den anropas samlas alla klientdata för sidan som begärts av besökaren.
title: Redigera körningsskript för referenssidans tagg
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 1%

---

# Redigera körningsskript för referenssidans tagg{#editing-the-reference-page-tag-execution-script}

Taggen för referenssidan består av ett körningsskript för sidtaggar som finns på en webbserver, och när den anropas samlas alla klientdata för sidan som begärts av besökaren.

Du kan ändra [!DNL Reference Page Tag Execution Script] om du vill samla in ytterligare information som kan identifieras under möten med Adobe Consulting Services-teamet. [!DNL Reference Page Tag Execution Script] är relativt liten för att undvika stora nedladdningstillägg på dina webbsidor.

Du får följande [!DNL Reference Page Tag Execution Script]-kod i en fil med namnet [!DNL zig.js]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

Gör så här för att underlätta datainsamling med [!DNL Reference Page Tag]:

1. Skapa eller placera bildfilen med 1 x 1 pixel och namnet [!DNL zag.gif] i en katalog som finns på webbservern.
1. Ändra cd-variabeln så att den refererar till rätt domän för webbplatsen eller den Adobe-hanterade tjänstdomänen som [!DNL zag.gif]-filen refereras till från. Referensen till filen skapas genom att köra filfunktionerna i [!DNL zig.js]. Exempel:

   ```
   //www.mysite.com
   ```

1. Ändra cu-variabeln så att den refererar till rätt sökväg till platsen för [!DNL zag.gif]-filen. Exempel

   ```
   /scripts
   ```

1. Kontrollera att rätt cachekontrollhuvuden har skapats för filerna [!DNL zag.gif] och [!DNL zig.js].
