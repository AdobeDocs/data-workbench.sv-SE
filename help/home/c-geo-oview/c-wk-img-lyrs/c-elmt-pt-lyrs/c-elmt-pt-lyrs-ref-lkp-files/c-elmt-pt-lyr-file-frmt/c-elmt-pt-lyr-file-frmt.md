---
description: Formateringsinformation om elementets punktlagerfil.
solution: Analytics
title: Filformat för elementpunktslager
topic: Data workbench
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filformat för elementpunktslager{#element-point-layer-file-format}

Formateringsinformation om elementets punktlagerfil.

Varje elementpunktslagerfil [!DNL .layer] som refererar till en uppslagsfil måste formateras med följande mall:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sökvägar </td> 
   <td colname="col2"> Sökväg till uppslagsfilen som innehåller latitud- och longituddata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitud-kolumn </td> 
   <td colname="col2"> Namnet på kolumnen i uppslagsfilen som innehåller longituddata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude-kolumn </td> 
   <td colname="col2"> Namnet på kolumnen i uppslagsfilen som innehåller latituddata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namnkolumn </td> 
   <td colname="col2"> Valfritt. Namnet på kolumnen i sökfilen som innehåller namnen på platserna som representeras av latitud- och longituddata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nyckelkolumn </td> 
   <td colname="col2"> <p>Namnet på kolumnen i uppslagsfilen som innehåller data för den gemensamma nyckeln, vilket gör att data-workbench-servern kan integrera data i uppslagsfilen i datauppsättningen. Detta måste vara den första kolumnen i sökfilen. </p> <p>Varje rad i den här kolumnen är ett element i en dimension. Den här dimensionen måste definieras i filen Transformation.cfg <span class="filepath"></span> eller en inkluderingsfil för transformeringsdatamängd och anges i dimensionsparametern för den här filen. Mer information om omvandlingskonfigurationsfiler finns i konfigurationsguiden för <i>datauppsättningar</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2">Namnet på dimensionen (definierad i en transformeringskonfigurationsfil) som innehåller element som motsvarar dataraderna i kolumnen <span class="wintitle"> Nyckel</span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mått </td> 
   <td colname="col2"> Namnet på mätvärdet som utvärderas över dimensionen som anges i Dimension-parametern. </td> 
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
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">Återgivningsläge 1. Punktstorleken definieras i skärmutrymmet (punkterna behåller en konstant storlek i förhållande till datorskärmen). Punkter återges med polygoner, så det finns ingen övre gräns för punktstorleken. Det här är standardåtergivningsläget. </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">Återgivningsläge 2. Punktstorleken definieras i världsrymden (punkterna behåller en konstant storlek i förhållande till världen). Punkter återges med polygoner, så det finns ingen övre gräns för punktstorleken. </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">Återgivningsläge 3. Punktstorleken definieras i skärmområdet. Punkter återges med hjälp av utjämnade punkter i OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Filen har följande [!DNL Zip Points.layer] format:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```

