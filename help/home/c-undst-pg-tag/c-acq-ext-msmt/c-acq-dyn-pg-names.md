---
description: För vissa webbplatser är det nödvändigt att använda inbäddade objektbegäranden för att skicka information till webbservern så att information om vilken sida som faktiskt betjänades kan hämtas av sensorn och användas för rapportering och analys.
solution: Analytics
title: Hämta dynamiska sidnamn
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hämta dynamiska sidnamn{#acquiring-dynamic-page-names}

För vissa webbplatser är det nödvändigt att använda inbäddade objektbegäranden för att skicka information till webbservern så att information om vilken sida som faktiskt betjänades kan hämtas av sensorn och användas för rapportering och analys.

Detta kan vara nödvändigt om sidans URL, som den visas av webbservern, inte indikerar det sidinnehåll som visas för webbläsaren. Det här fallet beror ofta på användningen av personalisering eller dynamiska innehållshanteringssystem där det faktiska innehåll som skickas på en sida avgörs direkt av webbadressen, cookien, relaterade data och programlogiken.

Implementeringen av ett inbäddat objekt för att samla in ytterligare mått bör ha minimal inverkan på webbplatsens övergripande prestanda. Adobe föreslår att du bäddar in en JavaScript-fil som det objekt som används för att samla in de utökade attributen. (Observera att en JavaScript-fil kan bäddas in utan att webblayouten och presentationen påverkas vilket kan leda till att en inbäddad bild används.) För att kunna hämta in den information som skickas i det inbäddade objektet föreslår Adobe även att ett gemensamt namn används. För namngivning hänvisar Adobe till detta objekt som [!DNL zig.js]. Filen ska [!DNL zig.js] skapas i lämplig katalog på en webbserver som [!DNL Sensor] är installerad på. Filen måste finnas så att begäran inte returnerar en felkod på 404. Innehållet i själva filen är inte viktigt. Du bör använda en tom fil med namnet [!DNL zig.js] för att minimera mängden nätverkstrafik som uppstår till följd av begäran.

För [!DNL Sensor] att kunna samla in ett användbart namn för sidan som faktiskt hanterades måste några rader JavaScript-kod läggas till på de dynamiska sidor som du vill spåra eller som du vill lägga till ett unikt sidnamn på. Den här koden bäddar in ett JavaScript-fragment på sidan, vilket gör att en tertiär inbäddad objektbegäran görs till webbservern när sidan läses in. Denna begäran skickar information om den specifika sida som återfanns på webbservern. Namnet på den sida som faktiskt hanterades överförs tillbaka till webbservern som en variabel i frågesträngen för det inbäddade objektet (i det här fallet JavaScript).

I allmänhet bör objektbegäran som är inbäddad på varje sådan HTML-sida se ut så här:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] säkerställer att [!DNL Sensor] loggar begäran trots [!DNL Sensor] filterreglerna för innehållstyp, som filtrering från JavaScript och bildbegäranden innan de lagras. Den deklarerade variabeln v_pn identifierar namnet på det faktiska sidinnehåll som skickas så att [!DNL Site] känner till namnet på sidan som besökaren faktiskt visade. v_pn-värdet kan etableras manuellt eller av annan skript eller programkod.

När värdet har samlats in kan du konfigurera data workbench-servern så att innehållet i frågesträngvariabeln (namn=värdepar, till exempel v_pn=Application Form) som har lagts till i [!DNL zag.gif] URI:n (till exempel [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), används som en utökning av [!DNL zag.gif] URI:n. Förutom de baslinjemått som erhållits vid varje HTTP-begäran, skulle en utökad mätning erhållas med denna begäran.

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_pn= | Värde som är associerat med v_pn-frågesträngsvariabeln | v_pn=Ansökningsformulär |

