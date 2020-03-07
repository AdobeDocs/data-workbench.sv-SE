---
description: När du skapar ett elementpunktslager som refererar till en sökfil för att få latitud- och longituddata, hämtas platsen för punkten genom att varje element och dess associerade latitud och longitud hämtas från sökfilen.
solution: Analytics
title: Definiera elementpunktslager som refererar till sökfiler
topic: Data workbench
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definiera elementpunktslager som refererar till sökfiler{#define-element-point-layers-referencing-lookup-files}

När du skapar ett elementpunktslager som refererar till en sökfil för att få latitud- och longituddata, hämtas platsen för punkten genom att varje element och dess associerade latitud och longitud hämtas från sökfilen.

>[!NOTE]
>
>I stället för att använda en sökfil kan du använda funktionen Dynamiska punkter, som bäddar in latituden och longituden för en plats i namnet på varje element i en dimension. Se [Definiera elementpunktslager med hjälp av dynamiska punkter](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512).

Om du vill definiera ett elementpunktslager som refererar till en sökfil måste du skapa eller redan ha tillgång till följande:

* **En dimension** som definieras i [!DNL Transformation.cfg file] eller en [!DNL transformation dataset include] fil. Mer information om omvandlingskonfigurationsfiler finns i *konfigurationsguiden* för datauppsättningar.

* **En uppslagsfil** som innehåller de data som används för att rita varje datapunkt. Den här filen måste innehålla minst tre kolumner med data för varje datapunkt: nyckeln, longituden och latituden. Mer information om det format som krävs för sökfilen finns i [Filformat](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)för elementpunktslager.

* **En lagerfil** som anger platsen för sökfilen och identifierar relaterade mått och mått samt nyckel-, longitud- och latitudkolumnsnamn i sökfilen. Mer information om det format som behövs för lagerfilen finns i [Elementpunktslagerfilformat](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

   >[!NOTE]
   >
   >Den [!DNL Zip Points.layer] fil som finns med i [!DNL Geography] profilen är ett elementpunktslager som identifierar [!DNL Zipcode.dim] filen, [!DNL Sessions.metric] filen, [!DNL Zip Points.txt] uppslagsfilen och namnen på nycklar, longitud, latitud och namnkolumner i uppslagsfilen.

## Filformat för elementpunktssökning {#section-0bc8c652c1bd40eb84078f2af71a5c06}

Sökfilen för elementpunktslagret måste innehålla minst följande tre kolumner:

* **[!DNL Key]kolumn:**Den här kolumnen ska innehålla data för vanliga nycklar, vilket gör att Data Workbench-servern kan ansluta data i sökfilen till data i datauppsättningen. Kolumnen måste vara den första kolumnen i uppslagsfilen[!DNL key]. Varje rad i den här kolumnen identifierar ett element i dimensionen.

* **[!DNL Longitude]kolumn:**Denna kolumn ska innehålla longituden för varje datapunkt i[!DNL Key]kolumnen.

* **[!DNL Latitude]kolumn:**Den här kolumnen ska innehålla latituden för varje datapunkt i[!DNL Key]kolumnen.

* **[!DNL Name]kolumn (valfritt):**Om du vill ange ett namn som ska visas på kartan för varje datapunkt, kan du inkludera en[!DNL Name]kolumn i sökfilen.

Varje rad i [!DNL Zip Points.txt] sökfilen innehåller en ZIP-kod i den första kolumnen följt av longitud, latitud och associerat stadsnamn.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## Lagerfilformat för elementpunkt {#section-52d7e92be8354d979af9e7a2210b76f2}

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
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
   <td colname="col2"> <p>Namnet på kolumnen i uppslagsfilen som innehåller data för den gemensamma nyckeln, vilket gör att Data Workbench-servern kan integrera data i uppslagsfilen i datauppsättningen. Detta måste vara den första kolumnen i sökfilen. </p> <p>Varje rad i den här kolumnen är ett element i en dimension. Den här dimensionen måste definieras i filen Transformation.cfg <span class="filepath"> eller en inkluderingsfil för en</span> transformeringsdatamängd <span class="wintitle"></span> och anges i dimensionsparametern för den här filen. Mer information om omvandlingskonfigurationsfiler finns i konfigurationsguiden för <i>datauppsättningar</i>. </p> </td> 
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
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">Återgivningsläge 1. Punktstorleken definieras i skärmutrymmet (punkterna behåller en konstant storlek i förhållande till datorskärmen). Punkter återges med polygoner, så det finns ingen övre gräns för punktstorleken. Det här är standardåtergivningsläget. </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">Återgivningsläge 2. Punktstorleken definieras i världsrymden (punkterna behåller en konstant storlek i förhållande till världen). Punkter återges med polygoner, så det finns ingen övre gräns för punktstorleken. </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">Återgivningsläge 3. Punktstorleken definieras i skärmområdet. Punkter återges med hjälp av utjämnade punkter i OpenGL. </li> 
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
