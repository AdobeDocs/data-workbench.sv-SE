---
description: Mätvärdena kan redigeras med Metrisk redigerare och sparas i katalogen Metrics för en profil.
solution: Analytics
title: Syntax för metriska uttryck
topic: Data workbench
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax för metriska uttryck{#syntax-for-metric-expressions}

Mätvärdena kan redigeras med Metrisk redigerare och sparas i katalogen Metrics för en profil.

Mer information finns i [Skapa och redigera härledda mått](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40). Måttuttryck kan också användas i kalkylblad. Mer information finns i [Kalkylblad](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). Följande syntax används för att definiera metriska uttryck.

Anteckningar:

1. Understrukna ord ska anges bokstavligen i uttryckstexten.
1. Formuläret {TEXT}? representerar valfri text.
1. Formuläret {TEXT}* representerar text som kan förekomma noll eller flera gånger.
1. Formuläret {A}| B| C|..} representerar text som består av exakt ett av de angivna alternativen, t.ex. A eller B eller C....
1. Formuläret [A,B) representerar ett nummerintervall, från A till men inte B.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifierare </p> </td> 
   <td colname="col2"> <p>En identifierare refererar till ett namngivet mätvärde. Mer information om reglerna för juridiska identifierare finns i <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Syntax för identifierare </a>. </p> <p>Exempel: Intäkter = Totalt_Pris </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Metrisk) </p> </td> 
   <td colname="col2"> <p>Resultatet av (Metrisk) är detsamma som resultatet av Metrisk. Parenteser anger ordningen för åtgärder i ett uttryck. </p> <p>Exempel: Medel = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Summan av resultaten av A- och B-mätningarna. </p> <p>Exempel: Värde = Intäkter + kostnadsbesparingar </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Skillnad i resultaten för A- och B-mätvärdena. </p> <p>Exempel: Vinst = Intäkt - Kostnad </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Produkt av resultaten av mätvärdena A och B. </p> <p>Exempel: Dollars = Cents * 0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A / B </p> </td> 
   <td colname="col2"> <p>Förhållandet mellan resultaten för mätvärdena A och B. </p> <p>Exempel: Intäkter_per_session = Inkomster/sessioner </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>Resultat av mätmetod A upphöjt till effekten av resultat av mätvärde B. </p> <p>Exempel: Område = Bredd^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>konfidensgrad (mått) </p> </td> 
   <td colname="col2"> <p>En uppskattning av standardavvikelsen för mätvärdet. Detta beräknas med hjälp av en provtagningsmetod som kallas schakknivning. </p> <p>Detta mått är minneskrävande och bör inte användas i stora tabeller. </p> <p>Om du vill använda den här syntaxen måste du ha en knivdimension (kallad"kniv") med lämpliga egenskaper. Mer information får du av Adobes konsulttjänster. </p> <p>Exempel: trust(Average_Score) </p> <p> <p>Obs!  Typerna av konfidensmått, inklusive konfidensmått (metrisk) och konfidensintervall (metrisk, schakniv), är särskilt användbara när du använder Adobes kontrollerade experimenteringsfunktioner. Om ett mätvärde hoppar från 12 % till 16 % under ett kontrollerat experiment kan du använda en självsäker pratbubbla för att beräkna sannolikheten för att hoppet berodde på slumpmässiga variationer. Detta kan hjälpa er att undvika att dra fel slutsatser av begränsade bevis och å andra sidan försäkra er om att en tvivelaktig förändring faktiskt är verklig. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>konfidensnivå (mätinstrument, jackkniv) </p> </td> 
   <td colname="col2"> <p>En uppskattning av standardavvikelsen för mätvärdet. Detta beräknas med hjälp av en provtagningsmetod som kallas schakknivning. Med den här syntaxen kan du avgöra om ett mätresultat är tillförlitligt med hjälp av en knivdimension som heter något annat än"jackkniv". </p> <p>Detta mått är minneskrävande och bör inte användas i stora tabeller. </p> <p>Om du vill använda den här syntaxen måste du ha en knivdimension (som kallas något annat än"kniv") med lämpliga egenskaper. Mer information får du av Adobes konsulttjänster. </p> <p>Exempel: trust(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Hanterar innehållet i cellen som du refererar till som ett måttuttryck. Syntaxen kan bara användas i en kalkylbladsvisualisering. </p> <p>Exempel: eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>Den matematiska logaritmfunktionen: Mått X är parametern och mått B är basen. </p> <p>Exempel: dB = 20*log(Amplitude,10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrisk[Filter] </p> </td> 
   <td colname="col2"> <p>"Mått där filter används": Ett nytt mätvärde som filtreras av det angivna filtret. </p> <p>Exempel: Jan_Sessions = Sessions[ Month="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mått efter dimension </p> </td> 
   <td colname="col2"> <p>Ett mätvärde utvärderat vid dimensionens nivå. Resultatet av (M med X)[F] (resultatet av mätvärdet "M med X" utvärderat med filtret "F") är resultatet av M[F med X] (resultatet av mätvärdet "M" utvärderat med filtret "F med X"). </p> <p>Exempel: AB_Visitors = </p> <p>(Besökare per session)[Page="A" and Page="B"] = </p> <p>Besökare[(Page="A" och Page="B") per session] = </p> <p>Antalet besökare som besökt sida A och sida B under samma session. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>tal </p> </td> 
   <td colname="col2"> <p>Ett mätvärde med ett fast värde. </p> <p>Exempel: Pi = 3,1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(metrisk) </p> </td> 
   <td colname="col2"> <p>Ignorerar alla dimensioner som måttet utvärderas över. Måttet har samma värde för alla element i den dimensionen. </p> <p>Exempel: Pct_of_Visitors = Visitors / total(Visitors) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(metrisk) </p> </td> 
   <td colname="col2"> <p>Ignorerar filter som tillämpas på måttet. Måtten påverkas inte av markeringar och andra filter. </p> <p>Exempel: Benchmark_sessioner = all( sessioner ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(metrisk)) </p> </td> 
   <td colname="col2"> <p>Ignorerar alla filter och dimensioner. Den har samma värde i en viss profil oavsett vilka filter eller dimensioner som används. </p> <p>Exempel: Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Ett mätvärde som ger antalet räkningsbara dimensioner som Besök eller Session. </p> <p>Exempel: Besökare = summa(en,Besökare) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_Dimension, Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Ett mätvärde som ger summan av en numerisk dimension över en räkningsbar dimension. Ordningstalen (till skillnad från formaterade värden) för elementen i den numeriska dimensionen används, så en skalfaktor måste ofta tillämpas på resultatet. </p> <p>Exempel: Värde = summa(sessionens_värde, session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>De mindre resultaten av mätvärdena A och B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>Det större av resultaten för mätvärdena A och B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>Ett mätvärde som är identiskt med mätresultat A, förutom att formateringsfunktionen för mätresultat B används. </p> </td> 
  </tr> 
 </tbody> 
</table>

