---
description: Taggen för referenssidan består av ett körningsskript för sidtaggar som finns på en webbserver, och när den anropas samlas alla klientdata för sidan som begärts av besökaren.
title: Redigera körningsskript för referenssidans tagg
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 1%

---

# Redigera körningsskript för referenssidans tagg{#editing-the-reference-page-tag-execution-script}

{{eol}}

Taggen för referenssidan består av ett körningsskript för sidtaggar som finns på en webbserver, och när den anropas samlas alla klientdata för sidan som begärts av besökaren.

Du kan ändra [!DNL Reference Page Tag Execution Script] Samla in ytterligare information som kan identifieras under kravsammankomster och samla in möten med Adobe konsulttjänster. The [!DNL Reference Page Tag Execution Script] är relativt liten för att undvika stora nedladdningstillägg på webbsidorna.

Följande [!DNL Reference Page Tag Execution Script] koden finns i en fil med namnet [!DNL zig.js]:

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

Att underlätta datainsamling genom att använda [!DNL Reference Page Tag]utför du följande steg:

1. Skapa eller montera en bildfil med namnet 1 x 1 pixel [!DNL zag.gif] till en katalog som finns på webbservern.
1. Ändra cd-variabeln så att den refererar till rätt domän för din webbplats eller Adobe-hanterade tjänstdomän som den [!DNL zag.gif] filen refereras. Referensen till filen skapas genom att körningen av [!DNL zig.js] filfunktioner. Exempel:

   ```
   //www.mysite.com
   ```

1. Ändra Cu-variabeln så att den refererar till rätt sökväg till platsen för [!DNL zag.gif] -fil. Exempel

   ```
   /scripts
   ```

1. Se till att rätt cachekontrollhuvuden har skapats för [!DNL zag.gif] och [!DNL zig.js] filer.
