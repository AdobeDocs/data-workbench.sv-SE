---
description: Anropet om körning av referenssidans tagg infogas på webbsidor som du vill samla in mätdata för.
title: Lägga till körningsanrop för referenssidkod
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Lägga till körningsanrop för referenssidkod{#adding-reference-page-tag-execution-calls}

{{eol}}

Anropet om körning av referenssidans tagg infogas på webbsidor som du vill samla in mätdata för.

Den bör tas med i HTML-dokumentets brödtext och kan placeras i en global inkluderingssidfot om tillämpligt. The [!DNL Reference Page Tag Execution Call] kan ändras av ditt team för att samla in ytterligare information som kan identifieras under möten med Adobe Consulting Services-teamet.

Att underlätta datainsamling genom att använda [!DNL Reference Page Tag]utför du följande steg:

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

1. Ändra sökvägen till platsen för [!DNL zig.js] och [!DNL zag.gif] filer. Exempel:

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Kontrollera att rätt rubriker för HTTP Cache-Control har angetts på webbservern för att säkerställa att [!DNL zig.js]och [!DNL zag.gif] filer cachelagras inte av webbläsaren. Du kan ange rubrikinformation för HTTP-cache-Control på något av två sätt. Den första metoden är att ange en HTTP-rubrik via webbservern. Den andra metoden är att ange ett HTTP-huvud för varje specifik sida eller inbäddat objekt med hjälp av skript. Med skriptmetoden måste webbsidan ha skapats med ett programmeringsspråk som JSP eller ASP. Sidan skriptas sedan så att rätt rubrikinformation skickas. Det finns två uppenbara nackdelar med denna metod: 1) alla sidor måste kodas för att sidhuvudet ska kunna skickas, och 2) sidorna kan inte vara statiska HTML, vilket påverkar webbserverns prestanda.

Webbplatser som körs på Microsoft IIS kan lägga till rätt HTTP-huvud via Microsoft Management Console. Webbplatser som hanteras från Netscape iPlanet-webbservrar kan uppnå detta genom att redigera [!DNL obj.conf] i platsens konfigurationskatalog. Apache Web Server ger webbmallarna möjlighet att anpassa HTTP-rubriker med den medföljande mod_headers-modulen där AOLServer kan anpassas med hjälp av TLS-moduler. Innan du implementerar rubriker för HTTP Cache-Control bör du läsa den dokumentation som är specifik för webbserverplattformen.

I allmänhet bör HTTP-huvudet vara strukturerat på följande sätt:

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
