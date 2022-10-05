---
description: Konceptuell information om kalkylbladsuttryck och användning av cellreferenser.
title: Kalkylbladsuttryck
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 1%

---

# Kalkylbladsuttryck{#worksheet-expressions}

{{eol}}

Konceptuell information om kalkylbladsuttryck och användning av cellreferenser.

Följande kalkylblad innehåller information om de besökare som visar programguidesidan som finns i onlineansökningsformuläret på en banks webbplats.

![](assets/client-wkst.png)

* Kolumn A visar en lista över de besökskategorier som utvärderas: besökare, refererade besökare och refererade besökare från hänvisande A.
* I kolumn B visas antalet besökare i varje kategori som visade sidan Använd nu.
* Kolumn C visar de besökare som har visat både Apply Now- och Application Wizard-sidorna.
* Kolumn D innehåller procentsatserna för Apply Now-visningsprogram i de tre kategorier som även visade sidan Application Wizard (Programguiden).

Kalkylbladet visar att ungefär 55 procent av de besökare som refereras från Referer A som visade sidan Använd nu också visade sidan Programguide.

I följande tabell visas exempelformler för kalkylbladet i föregående exempel:

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kalkylbladscell </th> 
   <th colname="col2" class="entry"> Formel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>Besökare som visade sidan Använd nu </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Besökare[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Refererade besökare som visade sidan Använd nu </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Refererade_besökare[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Refererade besökare från hänvisande A som visade sidan Använd nu </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Refererade_besökare[Page="/applynow/default.asp" </span> </p> <p> OCH <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Besökare som visade sidan Använd nu och sidan Programguiden </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Besökare[Page="/applynow/default.asp" </span> </p> <p> OCH <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Refererade besökare som visade sidan Använd nu och sidan Programguiden </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Refererade_besökare[Page="/applynow/default.asp" </span> </p> <p> OCH <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Refererade besökare från hänvisande A som visade sidan Använd nu och sidan för programguiden </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Refererade_besökare[Page="/applynow/default.asp"</span> </p> <p> OCH <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> OCH <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Procentandel besökare som visade sidan Använd nu och sidan Programguiden </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Procentandel refererade besökare som visade sidan Använd nu och sidan för programguiden </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Procentandel refererade besökare från referent A som visade sidan Använd nu och sidan för programguiden </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Precis som med andra visualiseringar uppdateras kalkylblad automatiskt när du gör en markering i en annan visualisering på arbetsytan. Mer information om hur du markerar finns i [Göra markeringar i visualiseringar](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

I följande exempel på webbdata har flera dagar med sessionsdata valts i visualiseringen Sessioner efter dag. Kalkylbladet visar att ungefär 69 procent av besökarna från Referer A som visade sidan Använd nu under den valda tidsramen även visade sidan Programguide. Utan detta val (som visas i exemplet ovan) visade ungefär 55 procent av besökarna från Referer A sidan Använd nu och sidan Programguide.

![](assets/client-exp.png)

## Använda cellreferenser {#section-0004e315c9c94d359b1a8a39794ba555}

Du kan ersätta valfri sträng, oavsett om den är för sig eller i ett annat uttryck i kalkylbladet, med en cellreferens.

* **Enkel cellreferens:** Cell A2 innehåller textbesökarna, som används som rubrik. Cell B2 innehåller [!DNL eval(A1)], som utvärderas till [!DNL =Visitors].

* **Filtercellsreferens:** Cell A5 innehåller gårdagens datum. Cell B5 innehåller [!DNL Visitors[ Day=A5 ]], som utvärderas till antalet besökare igår.

* **Sammanfogad cellreferens:** Cell A5 innehåller dagens datum och cell A6 innehåller tiden 08:00 till 08:59 för en timme. Cell B6 innehåller [!DNL Visitors[ Hour=A5+” ”+A6 ]], som beräknas till antalet besökare idag mellan 08:00 och 09:00.
