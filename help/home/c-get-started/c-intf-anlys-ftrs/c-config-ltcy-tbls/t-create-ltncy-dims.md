---
description: Latensdimensioner skapas från en överordnad räkningsbar dimension, till exempel sessioner, och en tidsdimension, till exempel Dag.
title: Skapa en latensdimension
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 0%

---

# Skapa en latensdimension{#create-a-latency-dimension}

Latensdimensioner skapas från en överordnad räkningsbar dimension, till exempel sessioner, och en tidsdimension, till exempel Dag.

När du skapar en latenstabell i Data Workbench lägger du automatiskt till en latensdimension i visualiseringsfilen (.vw). Du kan redigera en tabells fördröjningsdimension genom att följa stegen nedan.

**Redigera en fördröjningsdimension**

1. Öppna latenstabellen som du skapade i en textredigerare som Anteckningar. Den finns i mappen User > `working profile name` > Work i Datans Workbench installationskatalog.

   Den definierade latensdimensionen innehåller de parametrar som visas i följande exempel. (Definitionen av din fördröjningsdimension kan innehålla ytterligare parametrar.) [!DNL line entity = LatencyDim:] anger början på latensdimensionens definition.

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. Redigera värdena för parametrarna Namn, Nivå, Klipp, Tid, Format, Tid före eller Tid efter med följande tabell som vägledning:

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> För den här parametern.. </th> 
      <th colname="col2" class="entry"> Ange den här informationen... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Namn </p> </td> 
      <td colname="col2"> <p>Valfritt. Namnet på latensdimensionen som visas på snabbmenyn när du högerklickar på dimensionsetiketten eller elementen. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Nivå </p> </td> 
      <td colname="col2"> <p>En räkningsbar dimension som är överordnad till latensdimensionen. Exempel är session, besökare och sidvy. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Klipp </p> </td> 
      <td colname="col2"> <p>En räkningsbar dimension som har en 1:N-relation med latensdimensionens nivå. Latens beräknas inte över dimensionens gränser. Om du till exempel anger en nivå i sidvyn och ett klipp med sessioner, beräknas fördröjningar för de sidvyer som inträffade under samma session som händelsen. </p> <p>Mer information om enkla 1:N-dimensioner finns i <i>Konfigurationshandboken för datauppsättningar</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tid </p> </td> 
      <td colname="col2"> <p>Dimensionen som används för att mäta förfluten tid för latensdimensionen. Dimensionen kan vara en tidsdimension, till exempel Dag eller Timme, eller en räkningsbar dimension, till exempel Besök, Session eller Sidvy. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Format </td> 
      <td colname="col2"> <p>Valfritt. Anger utseendet på fördröjningsvisualiseringen i Data Workbench. I parametern Format kan du redigera följande värden: 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Tidssträng. Den tidsenhet som visas i tidsfördröjningsvisualiseringen, till exempel dag eller vecka. Var noga med att ändra tidssträngen när du ändrar tidsdimensionen. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Förskjutning. Ett heltal som är lika med negativ för värdet för Tid före. Om exempelvis Tid före är 7 ska förskjutningen vara -7. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tid före </p> </td> 
      <td colname="col2"> <p>Den maximala tiden (uttryckt i enheter för tidsdimensionen) före den händelse för vilken fördröjningen beräknas. Om värdet är 0 eller inte inställt alls beräknas fördröjningen endast för framåtriktningen. </p> <p>Om du ändrar det här värdet måste du ändra förskjutningsvärdet i parametern Format: Förskjutningen är negativ för värdet för Tid före. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Tid efter </p> </td> 
      <td colname="col2"> <p>Den maximala tiden (uttryckt i enheter för tidsdimensionen) efter den händelse för vilken fördröjningen beräknas. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Spara [!DNL .vw]-filen i användar-\*arbetsprofilens namn*\Arbetsmapp.

   Här följer inställningarna för standardfördröjningsdimensionen:

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   I följande fördröjningsdimension beräknas latensen för varje sessionshändelse i timmar och tiden före är inställd på noll. Därför beräknas fördröjningen endast för sessioner som inträffade inom 24 timmar efter den definierade händelsen.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
