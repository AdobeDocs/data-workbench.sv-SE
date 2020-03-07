---
description: Anropet om körning av referenssidans tagg infogas på webbsidor som du vill samla in mätdata för.
solution: Analytics
title: Lägga till körningsanrop för referenssidkod
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lägga till körningsanrop för referenssidkod{#adding-reference-page-tag-execution-calls}

Anropet om körning av referenssidans tagg infogas på webbsidor som du vill samla in mätdata för.

Den ska inkluderas i HTML-dokumentets brödtext och kan placeras i en global inkluderingssidfot om tillämpligt. Ditt team [!DNL Reference Page Tag Execution Call] kan ändra inställningarna för att samla in ytterligare information som kan identifieras under kravsammankomster med möten i Adobe Consulting Services-teamet.

Gör så här för att underlätta datainsamling med hjälp av [!DNL Reference Page Tag]verktyget:

1. Kopiera följande kod till HTML-dokumentets brödtext:

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. Ändra sökvägen till platsen för [!DNL zig.js] - och [!DNL zag.gif] -filerna. Exempel:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Kontrollera att rätt rubriker för HTTP Cache-Control har angetts på webbservern för att säkerställa att webbläsaren inte cachelagrar [!DNL zig.js]och [!DNL zag.gif] filer. Du kan ange rubrikinformation för HTTP-cache-Control på något av två sätt. Den första metoden är att ange en HTTP-rubrik via webbservern. Den andra metoden är att ange ett HTTP-huvud för varje specifik sida eller inbäddat objekt med hjälp av skript. Med skriptmetoden måste webbsidan ha skapats med ett programmeringsspråk som JSP eller ASP. Sidan skriptas sedan så att rätt rubrikinformation skickas. Det finns två uppenbara nackdelar med denna metod: 1) alla sidor måste kodas för att sidhuvudet ska kunna skickas, och 2) sidorna kan inte vara statisk HTML, vilket påverkar webbserverns prestanda.

Webbplatser som körs på Microsoft IIS kan lägga till rätt HTTP-huvud via Microsoft Management Console. Webbplatser som hanteras från Netscape Planet Web Servers kan uppnå detta genom att redigera [!DNL obj.conf] filen i platsens konfigurationskatalog. Apache Web Server ger webbmallarna möjlighet att anpassa HTTP-rubriker med den medföljande mod_headers-modulen där AOLServer kan anpassas med hjälp av TLS-moduler. Innan du implementerar rubriker för HTTP Cache-Control bör du läsa den dokumentation som är specifik för webbserverplattformen.

I allmänhet bör HTTP-huvudet vara strukturerat på följande sätt:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
