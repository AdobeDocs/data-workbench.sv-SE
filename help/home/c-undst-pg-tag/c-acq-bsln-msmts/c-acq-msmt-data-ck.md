---
description: Som en del av den insamlade baslinjemätningsinformationen samlar sensorn in de domäncookies som skickas från en besökares dator när en begäran görs från webbservern.
title: Hämta mätdata via cookies
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---

# Hämta mätdata via cookies{#acquiring-measurement-data-through-cookies}

Som en del av den insamlade baslinjemätningsinformationen samlar sensorn in de domäncookies som skickas från en besökares dator när en begäran görs från webbservern.

Detta inkluderar både beständiga cookies och sessionscookies som anges på webbplatsen när en besökare interagerar med systemet.

I de flesta fall anger webbplatser beständiga cookies för att identifiera besökare eller samla in användarindata för användning i efterföljande besökarsessioner. All information som skrivs till och lagras i beständiga cookies kan hämtas och användas tillsammans med alla andra mätdata i data workbench-servern.

Ett exempel på en sådan beständig cookie kan innehålla en kundidentifierare i form av en numerisk nyckel som finns i en domänspecifik cookie som finns på besökarens dator. Förutom att identifiera användaren som en återkommande besökare kan den beständiga cookien även användas för att ytterligare identifiera besökaren som en återkommande kund eller för att knyta besökaren till information som finns i en kunddatabas så att demografisk information som är offline kan visas i [!DNL Site] och användas för interaktiv analys.

Sessionscookies kan vara en bra mekanism för att samla in användarindata via formulärfält eller andra dynamiska interaktiva element på webbplatsen. Om en webbplats implementerar formulär för att hämta användarspecifika indata finns informationen kvar i sessionscookien endast så länge som sessionen är aktiv. När en användare lämnar webbplatsen eller sedan avslutar en session, lagras inte längre informationen på användarens dator. Den angivna informationen hämtas dock av [!DNL Sensor] och görs tillgänglig som mätdata i [!DNL Site].

Här följer ett exempel på hur du använder en sessionskaka för att fånga en enda formulärvariabel som anges av en besökare.

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

I det här exemplet anropas en funktion för att ange en sessionscookie på besökarens dator med fältnamnet och det värde som anges i formulärfältet. När formuläret skickas och den efterföljande webbsidan begärs, skickas sessionscookie-uppsättningen till webbservern och samlas in av [!DNL Sensor]. Följande data är därför tillgängliga på data workbench-servern för användning vid dataanalys:

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_1 | Värdet som är associerat med v_1-cookien. Detta värde representerar det NAMN som anges i formulärfältet som resulterade i att sessionscookien angavs. | v_1=Sven Svensson |

Sessionscookies kan också användas för att iterativt hämta formulärfält eller en mängd inbäddade JavaScript-variabler som finns på en HTML-sida. I följande exempel används JavaScript för att rekursivt hämta formulärfält som finns i en HTML-fil och ange en sessionscookie med rätt namn=värde-par.

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

I det här exemplet anges en sessionscookie på besökarens dator med namnet och värdet för alla formulärfält som finns i formuläret. Detta inkluderar inmatningsfält, kryssrutor, alternativknappar, kryssrutor och textområden. Som du kanske märker i det här exemplet, eftersom antalet formulärfält är okänt, är det nödvändigt att samla alla formulärnamn- och fältvärden som en enda sträng, avgränsade med ett et-tecken. Detta steg måste utföras på grund av en begränsning av antalet cookies som en användare kan ha på sin dator vid ett tillfälle. Endast tjugo (20) sessionscookies får finnas innan den äldsta släpps.
