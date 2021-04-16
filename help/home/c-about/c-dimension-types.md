---
description: Det finns flera typer av dimensioner på data workbench-servern. Därför är det viktigt att du känner till dimensionstypen när du använder en dimension för att skapa mått, filter eller härledda dimensioner.
title: Dimensioner
uuid: 07659373-8d9b-473d-8daa-ca8e7ac4afe8
exl-id: cbc25504-2c1c-4622-adc1-c9bbac8e12fb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 0%

---

# Dimensioner{#dimension-types}

Det finns flera typer av dimensioner på data workbench-servern. Därför är det viktigt att du känner till dimensionstypen när du använder en dimension för att skapa mått, filter eller härledda dimensioner.

Insight Server kan skapa och underhålla följande typer av dimensioner:

<table id="table_1A79B6C57ED145B6AA3BB05DD37AAD1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensioner </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Inventerbar </td> 
   <td colname="col2">En dimensionstyp där antalet element i dimensionen kan räknas av systemet. Räknbara dimensioner måste härledas från andra räkningsbara dimensioner. Räknbara dimensioner kan vara överordnade av andra dimensioner eller underordnade av andra räkningsbara dimensioner. <p>Exempel: Besökare, session, sidvy, bokning och beställning. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enkel </td> 
   <td colname="col2">En dimension som har en 1:N-relation med en överordnad räkningsbar dimension. En enkel dimension kan tolkas som att den representerar en egenskap för element av dess överordnade dimension. <p>Exempel: Besökarrefereraren är en enkel dimension med en överordnad till Visitor-dimensionen. Varje besökare kan bara ha en besökarreferent (sin första HTTP-referent), men många besökare kan ha samma besökarreferent. Därför är besökarreferenten"en-till-många" med besökardimensionen. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeriskt </td> 
   <td colname="col2">En dimension som har sorterat numeriska värden och en 1:N-relation med en överordnad räkningsbar dimension. En numerisk dimension kan tolkas som att den representerar en numerisk egenskap för elementen i dess överordnade dimension. Numeriska dimensioner används ofta för att definiera summamått. <p>Exempel: Den numeriska dimensionen Sessionsintäkt definierar intäkten, i dollar, för varje session. Varje session har ett enda intäktsbelopp, men ett valfritt antal sessioner kan ha samma intäkt, så sessionsintäkten är"en-till-många" med session. Ett mått för "Intäkt" kan definieras som <span class="filepath"> summa(Session_Revenue, Session)</span>, vilket ger den totala intäkten för de valda sessionerna. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Många-till-många </td> 
   <td colname="col2">En dimension som har en många-till-många-relation med en överordnad räkningsbar dimension. En många-till-många-dimension kan tolkas som att den representerar en"uppsättning" med värden för varje element i dess överordnade dimension. En många-till-många-dimension motsvarar en (anonym) räkningsbar dimension med dess överordnade dimension och en enkel dimension med en överordnad till den anonyma räkningsbara dimensionen. <p>Exempel: Sökfasen för många-till-många-dimensionen har en överordnad session. Varje session kan använda noll eller flera sökfraser och en sökfras kan användas i valfritt antal sessioner. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2">En dimension som har en 1:1-relation med en överordnad räkningsbar dimension. Elementnamnen för den normala dimensionen kan innehålla information om motsvarande element i den överordnade dimensionen. En normal dimension kan tolkas som att ett godtyckligt strängvärde lagras för varje element i det överordnade elementet. Denormala dimensioner kan användas med Insight Servers segmentexportfunktion för att få fram information om en delmängd eller ett segment av en räkningsbar dimension. Dessutom kan vanliga dimensioner refereras i metriska formler och kalkylbladsvisualiseringar och kan användas (med vissa begränsningar) för att definiera filter. <p>Exempel: Den normala dimensionens e-postadress har en överordnad till Visitor. Varje besökare har en e-postadress och varje element i e-postadressen är associerat med en enskild besökare. Även om två besökare har samma e-postadress är adresserna olika i e-postadressen. En segmentexport kan referera till e-postadressen för att skicka e-postadressen för varje besökare i ett segment. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tid </td> 
   <td colname="col2">En dimension som gör att du kan skapa en uppsättning periodiska eller absoluta mått för lokal tid (t.ex. Dag, Veckodag, Timme på dagen och så vidare) baserat på ett tidsstämpelfält som du anger. När du definierar tidsdimensioner kan du också välja en annan dag än måndag som ska användas som början av en vecka genom att ange parametern Startdag för vecka. <p>Exempel: Sessionstiden för tidsdimensionen har en överordnad session. Därför definierar dimensionen en uppsättning tidsdimensioner (dag, veckodag, timme, timme på dagen, månad och vecka) vars element motsvarar de tider då besökarnas sessioner på webbplatsen började. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Härledd </td> 
   <td colname="col2">Härledda dimensioner, i stället för att definieras i datauppsättningskonfigurationen baserat på de data som bearbetas, definieras i profilen baserat på andra dimensioner eller mätvärden. Många härledda dimensioner skapas automatiskt för att skapa olika typer av visualiseringar. <p>När en användare skapar en webbplats- eller processkarta skapar Insight Server i tysthet en Prefix-dimension. Andra, t.ex. måtten för rapporttiden, definieras av filer i katalogen Dimensioner i en profil. </p></td> 
  </tr> 
 </tbody> 
</table>
