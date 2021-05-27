---
description: När du skapar ett elementpunktslager med hjälp av dynamiska punkter bäddas latitud- och longituddata in i varje element i dimensionen.
title: Definiera punktlager för element med hjälp av dynamiska punkter
uuid: f4b41969-329a-4c33-a8db-8d85597fa577
exl-id: 5f6e264c-5804-47fa-a3ca-8608a3f7e9d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 1%

---

# Definiera punktlager för element med hjälp av dynamiska punkter{#define-element-point-layers-using-dynamic-points}

När du skapar ett elementpunktslager med hjälp av dynamiska punkter bäddas latitud- och longituddata in i varje element i dimensionen.

Om du vill definiera ett elementpunktslager med hjälp av dynamiska punkter måste du skapa eller redan ha tillgång till följande:

* En dimension, definierad i filen [!DNL Transformation.cfg] eller en [!DNL transformation dataset include]-fil, där varje element innehåller strängen &quot;latitud,longitud&quot; eller &quot;latitud,longitud,namn&quot;.

   Anvisningar om hur du skapar en dimension finns i *Konfigurationshandboken för datauppsättningar*.

* En lagerfil som anger den relaterade dimensionen.

Mer information om vilket format som krävs för lagerfilen finns i [Elementpunktslagerfilformat](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section-0645fbc761c14bb986f3d6f02df407a0).

>[!NOTE]
>
>När du använder [!DNL Dynamic Points] är det viktigt att se till att dimensionens kardinalitet som anges i lagerfilen är rimlig. Om alla rader i en datauppsättning har olika latitud- och longitudvärden fylls dimensionerna snabbt upp och de flesta rader hamnar i ett Small Elements-element. Eftersom elementet Small Elements inte har någon latitud eller longitud visas det inte på jorden.

## Elementpunktslagerfilformat {#section-0645fbc761c14bb986f3d6f02df407a0}

Varje lagerfil för elementpunkter som använder dynamiska punkter måste formateras med följande mall:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2"> <p>Dimensionens namn (definierat i en transformationskonfigurationsfil), som måste innehålla element med strängen "latitud,longitud" eller "latitud,longitud,namn", enligt följande exempel: 
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181,-77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317,-77.8126, någonstans </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mått </td> 
   <td colname="col2"> Namnet på mätvärdet som utvärderas över dimensionen som anges i parametern Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamiska punkter </td> 
   <td colname="col2"> Aktiverar dynamiska punkter. Ange som true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skala </td> 
   <td colname="col2"> Valfritt. Värde som används för att ändra storlek på punkterna i lagret. Standardvärdet är 100. Ju större värde, desto större punkt och ett mindre värde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Färg </td> 
   <td colname="col2"> Valfritt. RGB-färgvektorn, som uttrycks som (röd, grön, blå). För varje färg i vektorn kan du ange ett värde mellan 0,0 och 1,0. (1.0, 0.0, 0.0) är till exempel ljusröd och (0.5, 0.5, 0.5) är grå. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Återgivningsläge </td> 
   <td colname="col2"> <p>Valfritt. Heltalsvärde som representerar det återgivningsläge som ska användas för lagret. De tre tillgängliga lägena är följande: 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">Återgivningsläge 1. Punktstorleken definieras i skärmutrymmet (punkterna behåller en konstant storlek i förhållande till datorskärmen). Punkter återges med polygoner, så det finns ingen övre gräns för punktstorleken. Det här är standardåtergivningsläget. </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">Återgivningsläge 2. Punktstorleken definieras i världsrymden (punkterna behåller en konstant storlek i förhållande till världen). Punkter återges med polygoner, så det finns ingen övre gräns för punktstorleken. </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">Återgivningsläge 3. Punktstorleken definieras i skärmområdet. Punkter återges med hjälp av utjämnade punkter i OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Filen [!DNL IP Coordinates.layer] har följande format:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
