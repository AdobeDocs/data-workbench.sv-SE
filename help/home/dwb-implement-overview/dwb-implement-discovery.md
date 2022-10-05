---
description: Samla in och beskriv de affärsfrågor som passar er marknadsföringsmiljö när ni implementerar Data Workbench.
title: Data Workbench Discovery och krav
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
exl-id: 25cc2940-800a-4ad2-a7bb-c343e3d65500
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# Data Workbench Discovery och krav{#data-workbench-discovery-and-requirements}

{{eol}}

Samla in och beskriv de affärsfrågor som passar er marknadsföringsmiljö när ni implementerar Data Workbench.

I det här avsnittet kan du samla in information om de frågor och uppgifter som krävs för att ta fram lösningar i Data Workbench (DWB), som kan ta upp dessa frågor på ett korrekt, entydigt och teknikoberoende sätt, med referenser till affärsterminologi och Adobe Analytics Premium lösning. Detta avsnitt innehåller information om dessa mål och tillhörande krav.

## Fas 1: Viktiga affärsmål/mål {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

I följande tabeller uppmanas du att identifiera din kundbas och analysera hur din DWB-implementering fungerar.

* Förstå kundbasen
* Förstå specifikt affärsfall (t.ex. effektiviteten hos självbetjäning och andra datakanaler/offlinedatakällor)

**Förstå kundbasen**

Förstå varför kunderna använder er webbplats, vilka utmaningar ni står inför och hur DWB kommer att hjälpa er utifrån er affärsmodell. Exempel: hur ni mäter, övervakar och analyserar era kunder för att korssälja andra produkter och tjänster, får en lista över aktiva användare, kontopenetration och andra mål.

| ID | Affärsfråga/krav | Prioritet | Fas | Beroenden |
|---|---|---|---|---|
| 1a | Specifik affärsfråga 1 | Hög/medel/låg | 1 | Vanlig nyckel, beroende på någon annan nyckel osv. |
| 1b | Specifik affärsfråga 2 | Hög | 1 | Valfritt beroende |

Analyskonstruktion

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Datakällor för arbetsyteanalys</td> 
   <td colname="col2"> Lägg till namn på arbetsyta </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioner och mått för arbetsytan krävs </p> </td> 
   <td colname="col2"> <p>Identifiera Dimensioner: </p> <p>Identifiera mått: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter, flaggor och verktyg för arbetsytan som behövs </td> 
   <td colname="col2"> <p>Identifiera segment: </p> <p>Identifiera verktyg: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vilka åtgärder kan härledas från den här analysen? </td> 
   <td colname="col2"> Förstå uppgifter och innehåll med specifika DWB-arbetsytor. </td> 
  </tr> 
 </tbody> 
</table>

## Fas 2: Specifika affärsärenden {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

Förstå andra datakällor och kanaler och lär dig hur dessa kommer att relatera till era affärsärenden.

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Affärsfrågor/krav </th> 
   <th colname="col3" class="entry"> Prioritet </th> 
   <th colname="col04" class="entry"> Fas </th> 
   <th colname="col4" class="entry"> Beroenden </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> Specifikt affärskrav 1 </td> 
   <td colname="col3"> <p>Hög/medel/låg </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Vanlig nyckel, beroende på någon annan nyckel, kontoflagga/identifierare osv. </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>Specifikt affärskrav 2 </p> </td> 
   <td colname="col3"> Hög/medel/låg </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Alla beroenden </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**Analyskonstruktion**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Datakällor för arbetsyteanalys
     </td> 
   <td colname="col2">
     Exempel på namn på arbetsyta </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioner och mått för arbetsytan krävs </p> </td> 
   <td colname="col2"> <p>Dimensioner: Definiera nödvändiga dimensioner. </p> <p>Mätvärden: Definiera mått som behövs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter, flaggor och verktyg för arbetsytan som behövs </td> 
   <td colname="col2"> <p>Segment: Identifiera era kundsegment. </p> <p>Systemutvärdering: Välj verktyg som krävs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vilka åtgärder kan härledas från den här analysen? </td> 
   <td colname="col2"> Vad du ska förstå från den här arbetsytan </td> 
  </tr> 
 </tbody> 
</table>

**Datakällor**

| Datakällor | Prioritet | Hur ofta tas data emot? |
|---|---|---|
| Site 1 Name report suite (RSID) | 1 | Varje timme |
| Namn på plats 2 (om sådant finns) (RSID) | 1 | Varje timme |
| Datakälla 1 (om tillämpligt) | 2 | Dagligen? |
| Datakälla 2 (om tillämpligt) | 3 | Dagligen? |
