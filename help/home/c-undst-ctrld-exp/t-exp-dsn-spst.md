---
description: Den här filen fungerar inte bara som ett kalkylblad, utan också som en referens till dina beslut om experimentet.
solution: Analytics,Analytics
title: Experimentera med kalkylblad
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
exl-id: 554790ab-1182-4481-87b0-e768ea769ddf
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Experimentera i designkalkylblad{#experiment-design-spreadsheet}

Den här filen fungerar inte bara som ett kalkylblad, utan också som en referens till dina beslut om experimentet.

Om du behöver hjälp med att utforma ditt experiment kan du använda det experimentella designkalkylbladet (som heter VS Controlled Experiment Design.xls som standard) som tillhandahålls av Adobe.

Kalkylbladet för experimentell design kan endast ge användbara statistiska slutsatser när det aktuella mätvärdet definieras som en procentandel av besökarna som uppfyller vissa kriterier. Det är alltså bara användbart när man testar en besöksbaserad måtthypotes.

**Utforma ett experiment med hjälp av designfilen för experimentet**

1. Om du har administratörsåtkomst till dina webb- eller programservrar navigerar du till installationsmappen för [!DNL Sensor] på valfri [!DNL Sensor]-dator i webbklustret. Om du inte har administratörsåtkomst kontaktar du kontohanteraren i Adobe för att begära filen.
1. Öppna filen VS Controlled Experiment Design.xls. (Du kan ändra namn på filen om du vill.)

   Kalkylbladet på följande sida är ett exempel på hur du skulle slutföra kalkylbladet när du förbereder testning av exempelhypotesen som används i hela den här guiden.

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. Ange text eller värden för alla fält i blått i den här filen, som beskrivs i följande tabell. Beräkningsfälten definieras i den andra tabellen.

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> I det här fältet.. </th> 
   <th colname="col2" class="entry"> Ange </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Experimenttitel </td> 
   <td colname="col2"> Ett beskrivande namn på ditt experiment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Experimentbeskrivning </td> 
   <td colname="col2"> En textbeskrivning av experimentet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mätning utförs </td> 
   <td colname="col2"> <p>Namnet på det mätvärde som experimentet baseras på. </p> <p>Exempel: Besökskonvertering </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Måttdefinition </td> 
   <td colname="col2"> <p>Definitionen av det mätvärde som experimentet baseras på. </p> <p>Format: Besökare[X]/Besökare </p> <p>Exempel: <span class="filepath"> Besökare[URI='conversionpage.asp']/Visitors</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avsedd starttid </td> 
   <td colname="col2"> Det datum och den tidpunkt då du vill att experimentet ska börja. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avsedd sluttid </td> 
   <td colname="col2"> Det datum och den tidpunkt då du vill att experimentet ska avslutas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tillämpliga val </td> 
   <td colname="col2"> (Valfritt) Dimensionsnamnet och elementuppsättningen eller det intervall som du vill segmentera datauppsättningen med ytterligare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Experimentera-URI:er </td> 
   <td colname="col2"> De URI:er som ingår i din hypotes. Du definierar aktuella URI:er för kontrollgruppen och de alternativa URI:er som du har skapat eller kommer att skapa för testgruppen/testgrupperna. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Förväntade mått för programmarkeringar </td> 
   <td colname="col2"> Rubrik för de måttvärden som du förväntar dig för webbplatsen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Genomsnittligt antal besökare per dag </td> 
   <td colname="col2"> Genomsnittligt antal besökare på din webbplats per dag. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besökskonvertering </td> 
   <td colname="col2"> Den genomsnittliga konverteringsgraden för besökare för webbplatsen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Experimentera avgör om mätnamnet för testgrupperna är ... </td> 
   <td colname="col2"> Rubrik för hur måttvärdena ska jämföras. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Större än värdet för kontrollgruppen? </td> 
   <td colname="col2"> Ställ in det här fältet på True om du vill kunna dra slutsatsen att testgruppens mått ökade under experimentet. Ställ in det här fältet på Falskt för att minska antalet besökare som behövs för att dra slutsatser. Adobe rekommenderar att du ställer in det på True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mindre än värdet för kontrollgruppen? </td> 
   <td colname="col2"> Ställ in det här fältet på True om du vill kunna dra slutsatsen att testgruppens mätvärden minskade under experimentet. Adobe rekommenderar att du ställer in det på True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minst (identifieringsnivå) </td> 
   <td colname="col2"> Procentvärdet som du vill att måttet för testgruppen ska vara högre eller lägre än för kontrollgruppen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Med en tillförlitlighetsnivå på minst </td> 
   <td colname="col2"> Den önskade konfidensnivån för testgruppsvärdena. Konfidensnivån avgör antalet falskt positiva för att mäta sannolikheten för att de angivna förväntningarna är sanna. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> och en effektnivå på </td> 
   <td colname="col2"> Den önskade effektnivån för testgruppens värden. Effektnivån bestämmer antalet falska negativ. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % av besökarna </td> 
   <td colname="col2"> Rubrik för procentandelen besökare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Testgrupp </td> 
   <td colname="col2"> Procent besökare som du vill inkludera i testgruppen. Du kan spela upp med den här siffran tills värdet i fältet Totalt (normalt 100 %) i avsnittet Besökare är lika med eller större än värdet i fältet Minimibesökare krävs (Test+Kontrollgrupper), som båda beskrivs i följande tabell. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kontrollgrupp </td> 
   <td colname="col2"> Procent besökare som du vill inkludera i kontrollgruppen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Andra Design Notes </td> 
   <td colname="col2"> Anteckningar som du vill spara för framtida referens. </td> 
  </tr> 
 </tbody> 
</table>

De återstående fälten beräknas baserat på de värden du har angett och beskrivs i följande tabell.

| Fält | Beskrivning |
|---|---|
| Förväntade mått för programmarkeringar | Rubrik för de måttvärden som du förväntar dig för webbplatsen. |
| Förväntade besökare per period | Det här fältet beräknas normalt automatiskt av kalkylbladet. Det bygger på antagandet att webbplatsen på de flesta dagar tar emot många fler besökare än besökare som återvänder. Om så inte är fallet bör cellens beräkning skrivas över med det faktiska antalet besökare som förväntas under försöket. |
| Beräknad Z-poäng för Type I-fel | Z-poängen för ett falskt positivt resultat. Detta är en mellanliggande statistisk beräkning. |
| Beräknad Z-poäng för typ II-fel | Z-poängen för ett falskt negativt resultat. Detta är en mellanliggande statistisk beräkning. |
| Minsta antal besökare som krävs (test+kontrollgrupper) | Minsta antal besökare som behövs i ditt experiment för att uppfylla din angivna konfidensnivå, effektnivå och Z-poäng, uttryckt i procent av värdet i fältet Förväntade besökare per period. |
| Minsta antal besökare som krävs (test+kontrollgrupper) | Minsta antal besökare som behövs i ditt experiment för att uppfylla din angivna konfidensnivå, energinivå och Z-poäng. Värdet måste vara mindre än eller lika med värdet i fältet Totalt (vanligtvis 100 %) i avsnittet Besökare. |
| Minimal experimenttid (dagar) | Minsta antal dagar du behöver köra ditt experiment för att uppfylla din angivna konfidensnivå, strömnivå och Z-poäng. Detta beräknade nummer kan ge samma problem som beskrivs i fältet Förväntade besökare per period. För en webbplats med många återkommande besökare är fältet Minimitid (dagar) det förväntade antalet dagar det tar att se ett antal unika besökare som är lika med värdet i fältet Minsta antal besökare som krävs. |
| Besökare | Rubrik för besökarnas värden. |
| Testgrupp | Antal besökare som behövs i testgruppen. |
| Kontrollgrupp | Antal besökare som behövs i kontrollgruppen. |
| Totalt (vanligen 100 %) | Totalt antal besökare som behövs för experimentet. Värdet måste vara lika med eller större än värdet i fältet Minsta antal besökare som krävs (Test+Control Groups). |
| Testgruppens exakthet (på målkonfidensnivå) | Procentandel som anger att det finns en risk som motsvarar den angivna konfidensnivån att det uppmätta värdet för mätvärdet som beräknas för testgruppen ligger inom denna procentandel av dess verkliga värde. |
| Kontrollgruppens noggrannhet (på målkonfidensnivå) | Procent som anger att det finns en risk som motsvarar den angivna konfidensnivån att det uppmätta värdet för det mätvärde som beräknas för kontrollgruppen ligger inom denna procentandel av dess verkliga värde. |
| Z-poäng (vid målprecision) | Antal standardavvikelser ett givet värde ligger från provningsmedelvärdet. |
| Faktisk konfidensnivå (vid målintervall) | Den konfidensnivå som uppnåtts för försöket. Konfidensnivån mäter sannolikheten för att de angivna förväntningarna är sanna. |
| Faktiskt intervall (på målkonfidensnivå) | Det konfidensintervall som uppnås för försöket, som ger ett uppskattat värdeintervall som sannolikt inkluderar en okänd populationsparameter. Detta intervall beräknas utifrån en given uppsättning exempeldata. |

Du måste titta på värdet i fältet Minimum Visitors Required (Test+Control Groups). . .

![](assets/Experiment_Design_Min_Visitors.png)

och jämför det med värdet i fältet Total i kolumnen [!DNL Visitors].

![](assets/Experiment_Design_Total_Visitors.png)

För att ditt experiment ska vara statistiskt giltigt måste värdet i fältet Totalt (normalt 100 %) vara lika med eller större än värdet i fältet Minimibesökare krävs (Test+Control Groups).

Med tanke på de inmatningar du fått visar exempeltabellen att 10 475 besökare måste delta i det här experimentet för att uppnå det angivna 95-procentiga konfidensintervallet (vilket är det minsta föreslagna förtroendet för ett kontrollerat experiment, även om du kan öka det antalet). Experimentet innehåller 30 000 besökare, vilket är mycket mer än det minsta antalet besökare som krävs.

Om du behåller antalet dagar kan du öka konfidensnivån så länge det totala antalet besökare fortsätter att uppfylla eller överskrida det obligatoriska minimiantalet.

1. Spara filen för referens och använd sedan informationen från filen för att konfigurera experimentet med hjälp av kalkylbladet för experimentkonfiguration. Mer information om det här kalkylbladet finns i [Konfigurera och distribuera Experimentet](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).
