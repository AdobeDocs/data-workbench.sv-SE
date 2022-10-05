---
description: En denormal dimension har en 1:1-relation med dess överordnade räkningsbara dimension.
title: Dimensioner
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
exl-id: 0c4fad38-bc7c-4b63-98ec-c9121e576a36
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 0%

---

# Dimensioner{#denormal-dimensions}

{{eol}}

En denormal dimension har en 1:1-relation med dess överordnade räkningsbara dimension.

Du definierar en normal dimension när den önskade dimensionen innehåller ett unikt element för varje element i dess överordnade. Till exempel: [!DNL EMail Address] är en denormal dimension med en överordnad till Visitor. Varje besökare har en e-postadress, och varje element i e-postadressen är e-postadressen till en enskild besökare. Även om två besökare har samma e-postadress är adresserna olika element i e-postadressen.

Du kan använda denorala dimensioner i alla tabellvisualiseringar, i detaljtabeller eller för att skapa filter. Dessutom kan du använda denorala dimensioner med data workbench-serverns segmentexportfunktion för att exportera fältvärden (till exempel [!DNL Tracking ID] eller [!DNL EMail Address]) som har många värden. Eftersom alla segmentdata som du vill exportera måste definieras som en dimension i profilen, måste du skapa en normal dimension som lagrar de råa strängarna för fältets data.

>[!NOTE]
>
>När du använder en denormal dimension i en tabell eller annan visualisering som förväntar sig en normal dimension, skapas en härledd denormal dimension automatiskt. Den härledda denorala dimensionen har en 1:N-relation med den överordnade dimensionen.

Mer information om visualisering och filter för detaljtabeller finns i kapitlet om analysvisualiseringar i *Användarhandbok för Data Workbench*. Mer information om segmentexport finns i kapitlet Konfigurera gränssnitt och analysfunktioner i *Användarhandbok för Data Workbench*.

>[!NOTE]
>
>Denormala dimensioner kan vara väldigt dyra när det gäller frågetid och diskutrymme. En normal dimension med överordnad [!DNL Page View]och en genomsnittlig indatasträng på 50 byte kan lägga till 25 GB data i buffertarna i en typisk, stor datauppsättning, vilket motsvarar cirka 13 enkla eller numeriska sidvisningsmått, eller cirka 125 sessionsnivådimensioner. Lägg aldrig till en normal dimension i en datauppsättning utan noggrann utvärdering av prestandapåverkan.

Denormala dimensioner definieras av följande parametrar:

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Beskrivande namn på dimensionen så som den visas i data workbench. Dimensionsnamnet får inte innehålla ett bindestreck (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Noteringar om den utökade dimensionen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor under vilka relationen mellan överordnad och inmatningsfältets värde ska skapas. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dold </td> 
   <td colname="col2"> Avgör om dimensionen visas i gränssnittet för data workbench. Som standard är den här parametern inställd på false. Om dimensionen till exempel bara ska användas som bas för ett mätresultat, kan du ställa in den här parametern på true för att dölja dimensionen från data workbench-visningen. </td> 
   <td colname="col3"> sant </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Värdet som är relaterat till den överordnade dimensionen (överordnad). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normaliserade element </td> 
   <td colname="col2"> En prestandajusteringsparameter som anger antalet dimensionselement vars namn ska lagras i systemminnet. Om du anger ett högre värde för den här parametern används mer RAM-minne, men det ger snabbare frågor. Standardvärdet är 16383. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Åtgärd </td> 
   <td colname="col2"> <p>Tillgängliga åtgärder är följande: </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> FÖRSTA ICKE-BLANK: Det första icke-tomma indatavärdet används, oavsett om det kommer från den första loggposten eller inte. If <span class="wintitle"> Indata</span> är ett vektorfält, används den första raden i vektorn för den aktuella loggposten. </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> FÖRSTA RADEN: Värdet för den första loggposten som är relaterad till det överordnade dimensionselementet används, även om indata är tomma. If <span class="wintitle"> Indata</span> är ett vektorfält, används den första raden i vektorn för den aktuella loggposten. Om värdet är tomt eller inte är ett tal, eller om den relevanta loggposten inte uppfyller dimensionens villkor, används inget värde. </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> SENASTE NONBLANK: Det sista icke-tomma indatavärdet används, oavsett om det kommer från den sista loggposten eller inte. If <span class="wintitle"> Indata</span> är ett vektorfält, används den första raden i vektorn för den aktuella loggposten. </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> SISTA RADEN: Värdet för den sista loggposten som hör till det överordnade dimensionselementet används, även om indata är tomma. If <span class="wintitle"> Indata</span> är ett vektorfält, används den första raden i vektorn för den aktuella loggposten. Om värdet är tomt eller inte är ett tal, eller om den relevanta loggposten inte uppfyller dimensionens villkor, används inget värde. </li> 
     </ul> </p> <p> <p>Obs! Om åtgärden inte ger något värde används ett tomt värde (""). </p> </p> <p> Du bör ange en åtgärd för att se till att dimensionen definieras som tänkt. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överordnad </td> 
   <td colname="col2"> Namnet på den överordnade dimensionen. Alla räkningsbara dimensioner kan vara en överordnad dimension. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Den denorala dimensionen som visas i det här exemplet tar alla data i fältet x-trackingid som indata och inkluderar dem i en dimension som heter Visitor-ID. För ett segment med besökare som du har skapat kan du exportera data i dimensionen för besökar-ID (samt andra definierade dimensioner).

![](assets/cfg_Transformation_Dim_Denormal.png)
