---
description: När du skapar ett elementpunktslager med hjälp av dynamiska punkter bäddas latitud- och longituddata in i varje element i dimensionen.
title: Definiera elementpunktslager med hjälp av dynamiska punkter
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
exl-id: ad849fe7-b909-40ef-835f-f1764e008de9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# Definiera elementpunktslager med hjälp av dynamiska punkter{#defining-element-point-layers-using-dynamic-points}

{{eol}}

När du skapar ett elementpunktslager med hjälp av dynamiska punkter bäddas latitud- och longituddata in i varje element i dimensionen.

Om du vill definiera ett elementpunktslager med hjälp av dynamiska punkter måste du skapa eller redan ha tillgång till följande:

* **En dimension**, som definieras i [!DNL Transformation.cfg] eller en inkluderingsfil för transformeringsdatamängd, där varje element innehåller strängen &quot;latitud,longitude&quot; eller &quot;latitud,longitud,name&quot;.

   Anvisningar om hur du skapar en dimension finns i *Konfigurationshandbok för datauppsättning*.

* **En lagerfil** som anger den relaterade dimensionen.

   Mer information om vilket format lagerfilen ska ha finns i [Filformat för elementpunktslager](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>När du använder [!DNL Dynamic Points]är det viktigt att säkerställa att kardinaliteten för den dimension som anges i lagerfilen är rimlig. Om alla rader i en datauppsättning har olika latitud- och longitudvärden fylls dimensionerna snabbt upp och de flesta rader hamnar i ett Small Elements-element. Eftersom elementet Small Elements inte har någon latitud eller longitud visas det inte på jorden.

## Filformat för elementpunktslager {#section-bbcc2baa2f754dba81eba93339a97cbd}

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

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
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
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181,-77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317,-77.8126, någonstans </li> 
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
   <td colname="col2"> Valfritt. Färgvektorn RGB, som uttrycks som (röd, grön, blå). För varje färg i vektorn kan du ange ett värde mellan 0,0 och 1,0. (1.0, 0.0, 0.0) är till exempel ljusröd och (0.5, 0.5, 0.5) är grå. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Återgivningsläge </td> 
   <td colname="col2"> <p>Valfritt. Heltalsvärde som representerar det återgivningsläge som ska användas för lagret. De tre tillgängliga lägena är följande: 
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">Återgivningsläge 1. Punktstorleken definieras i skärmutrymmet (punkterna behåller en konstant storlek i förhållande till datorskärmen). Punkter återges med polygoner, så det finns ingen övre gräns för punktstorleken. Det här är standardåtergivningsläget. </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">Återgivningsläge 2. Punktstorleken definieras i världsrymden (punkterna behåller en konstant storlek i förhållande till världen). Punkter återges med polygoner, så det finns ingen övre gräns för punktstorleken. </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">Återgivningsläge 3. Punktstorleken definieras i skärmområdet. Punkter återges med hjälp av utjämnade punkter i OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

The [!DNL IP Coordinates.layer] filen har följande format:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
