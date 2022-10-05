---
description: Lift- och Gain-diagrammen erbjuder visualiseringar för att utvärdera den potentiella prestandan hos en poängsatt modell för att utvärdera prestanda jämfört med definierade delar av målgruppen.
title: Ökning av benägenhet och börskursdiagram
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
exl-id: 5ac08512-ac9c-4e85-a4f9-ea6d819095d8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# Ökning av benägenhet och börskursdiagram{#propensity-gain-and-lift-charts}

{{eol}}

Lift- och Gain-diagrammen erbjuder visualiseringar för att utvärdera den potentiella prestandan hos en poängsatt modell för att utvärdera prestanda jämfört med definierade delar av målgruppen.

Vinst- och lyftdiagram är visualiseringar som byggs för att utvärdera den poängsatta modellens potentiella prestanda. Dessa diagram utvärderar prestanda för varje del av populationen.

**Öppna ett lyft- eller magasin-diagram**

1. Välj [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Hovra över **[!UICONTROL Model Complete]** av en sparad poäng.

![](assets/propensity_lift_gain_1.png)

**Om Lyft och förstärkning**

Lyft och förstärkning av diagram är användbara visuella verktyg för att mäta värdet i en prediktiv modell. Båda diagrammen består av en lyftkurva (grön) och en baslinje (rosa). För **Vinst**, representerar avståndet mellan lyftkurvan och baslinjen hur mycket du kan förbättra prestandan i svar (eller &quot;ökningen&quot;) jämfört med att använda det prediktiva läget. Ökningen uppnås genom att man prioriterar och målgruppsanpassar de potentiella kunder (kunder/besökare) som är mest benägna att konvertera, i stället för att marknadsföring görs till kunder/besökare på måfå. På så sätt kan du kvantifiera det förväntade värdet av att använda den prediktiva modellen för att välja vilka potentiella kunder som ska kontaktas.

Liknar Gain-diagrammet, **Lyft diagram** visar hur mycket större sannolikheten är att du får positiva svar än om du kontaktade potentiella kunder på måfå. Ni vill att avståndet mellan lyftkurvan och baslinjen ska vara så stort som möjligt, vilket motsvarar större förväntade vinster av att använda den prediktiva modellen för att kontakta kunderna. Matematiskt definieras öknings- och lyftdiagram enligt följande:

* **Ökning** = (Förväntat svar med prediktiv modell för kontaktpotentiell kund) / (Förväntat svar från slumpmässigt kontaktande potentiell kund)
* **Lyft** = (Förväntat svar bland en specifik gruppstorlek för potentiella kunder som identifieras med prediktiv modell) / (Förväntat svar bland samma specifika gruppstorlek för potentiella kunder som identifieras slumpmässigt)

**Exempel på Lyft och förstärkning av diagram**

Exempel: en återförsäljare som vill starta en e-postmarknadsföringskampanj för att sälja yoga-byxor. Historiskt sett förväntar sig analytikerna en genomsnittlig svarsfrekvens på 20 procent baserat på tidigare e-postmarknadsföringskampanjer som liknar denna. Även om analytikern har nästan 5 miljoner kunder i sin e-postdatabas vill företaget bara marknadsföra till de kunder som mest troligt svarar på e-post och inköp. På så sätt maximerar företaget avkastningen på kampanjerna samtidigt som det ser till att de inte skickar e-post i onödan till ointresserade kunder. Med en förväntad svarsfrekvens på 20 procent förväntar sig marknadsföraren och analytikern att ungefär 1 miljon kunder sannolikt kommer att svara och köpa. I stället för att slumpmässigt gissa vilka av dessa kunder som kommer att vara bland de 20 procenten av svaren vill analytikern vara smart när det gäller att förutsäga vilka av de 1 miljoner potentiella kunderna (bland de 5 miljoner kunder som finns i databasen) som är mest benägna att svara.

Med hjälp av Adobe Audience Scoring-funktionen definierar analytikern framgång när en potentiell kund klickar på ett e-postmeddelande och köper yoga-byxor (den beroende variabeln). När de oberoende variablerna har valts ut (baserat på erfarenheter och kunskaper som erhållits från analyser av bl.a. datakorrelationer och målgruppsklustring), beräknas varje potentiell kund utifrån sin sannolikhet att svara positivt på e-postmarknadsföringskampanjen (klicka på e-postmeddelandet och köpa yogbyxor). Analytikern öppnar de resulterande Gain- och Lift-diagrammen baserat på den prediktiva modellen.

Y-axeln visar procentandelen av de kumulativa förväntade positiva svaren. I vårt exempel förväntar vi oss totalt 1 miljon positiva svar. Ett värde på 20 % på y-axeln motsvarar 20 % av de 1 miljoner förväntade positiva svaren, eller 200 000 positiva svar. X-axeln visar hur många potentiella kunder som kontaktas. I vårt exempel representerar x-axeln en bråkdel av de 5 miljoner kunderna i e-postdatabasen. Baslinjen (rosa) är den totala svarsfrekvensen - om du kontaktar X% av potentiella kunder får du X% av det totala positiva svaret. Med hjälp av den prediktiva modellen visar lyfkurvan (grön) procentandelen positiva svar som erhållits (y-axel) genom att kontakta en viss procentandel av potentiella kunder (x-axel).

Lyft-diagrammet visar den förväntade lyften som ett resultat av att den prediktiva modellen används för att fastställa de 1 miljon mest sannolika möjligheterna att köpa yoga-byxor efter att ha tagit emot och klickat på e-postmeddelandet. Om du kontaktar 20 procent av de slumpmässigt utvalda potentiella kunderna utan någon prediktiv modell bör du förvänta dig att få 20 procent av respondenterna. Men om du använder den prediktiva modellen för att identifiera de 20 största procenten av de potentiella kunderna som är mest benägna att svara, förväntar du dig att få 50 % av respondenterna. Y-värdet för lyftkurvan vid 20 procent är 50/20 = 2,5. Lifdiagram visar hur mycket större sannolikheten är att du får svar än om du kontaktar ett slumpmässigt urval av potentiella kunder. Genom att till exempel kontakta endast 20 procent av de potentiella kunderna baserat på den prediktiva modellen kommer ni att nå 2,5 gånger så många respondenter som om ni inte hade använt någon prediktiv modell.
