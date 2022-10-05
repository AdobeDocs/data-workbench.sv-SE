---
description: Data workbench stöder både latitud- och longitudprojektioner och UTM-projektioner (Universal Transverse Mercator) för alla terrängbildslagerkällor.
title: Ange projektionsinformation för terrängbilder
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 0%

---

# Ange projektionsinformation för terrängbilder{#specify-projection-information-for-terrain-images}

{{eol}}

Data workbench stöder både latitud- och longitudprojektioner och UTM-projektioner (Universal Transverse Mercator) för alla terrängbildslagerkällor.

Projektionsinformation krävs för oprojicerade oprojicerade bitmappar och allmänna bilder, utan projicering. Du kan ange projektionsinformation för bilder med inbäddad projektionsinformation, men det är vanligtvis inte nödvändigt eftersom projektionsparametrarna bestäms automatiskt utifrån geodetiska data som är inbäddade i själva bilden. I följande avsnitt finns mer information om hur du anger dessa projektionsformat i [!DNL Terrain Images.cfg] -fil.

## Latitude-longitud - prognoser {#section-6e335357ec28462ba39c565e0a5986c7}

Projektionsformatet latitud-longitud (LatLonProjection) i [!DNL Terrain Images.cfg] filen definieras av fyra parametrar för latitud och longitud.

Om du vill ange en LatLonProjection för oprojicerade bilder (oprojicerade råbilder och allmänna bilder, oprojicerade) kan du ange inställningar för LatLonProjection i [!DNL Terrain Images.cfg] i Data Workbench.

Om du vill ange en LatLonProjection för bilder med inbäddad projektionsinformation måste du öppna [!DNL Terrain Images.cfg] i en textredigerare som Anteckningar, ange parametern Projection Info till LatLonProjection och lägg till inställningar för [!DNL LatLonProjection].

**Ange en LatLonProjection för oprojicerade bilder**

1. Öppna [!DNL Terrain Images.cfg] i Datan Workbench och lägga till en terrängbildlagerinskälla enligt beskrivningen i [Definiera ett terrängbildlager](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).
1. Redigera parametrarna för Projektionsinformation med följande parametertabell som vägledning:

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>Latituden på bildens överkant, i grader, där 90 är Nordpolen och -90 är Sydpolen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>Latitud för bildens nederkant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>Longitud för bildens vänstra kant, i grader, där positiva tal är öster och negativa tal är longituder väster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>Longitud för bildens högra kant. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Spara filen genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. Om du vill spara de lokalt gjorda ändringarna på Data Workbench-serverdatorn går du till [!DNL Server Files Manager], högerklicka på bockmarkeringen för [!DNL Terrain Images.cfg] i [!DNL Temp] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

**Ange en LatLonProjection för bilder i inbäddad projektionsinformation**

I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL Terrain Images.cfg] filen finns i den här katalogen.

Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Terrain Images.cfg]och sedan klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Terrain Images.cfg].

Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg] -filen visas i ett Anteckningsfönster.

Redigera parametrarna för projektionsinformation med följande exempelfilfragment som hjälp. Var noga med att specificera projektionstypen så som den markeras nedan. Beskrivningar av parametrarna finns i tabellen LatLonProjection Parameters i föregående procedur.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Universal Transverse Mercator Projection {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

UTM-projektionen (Universal Transverse Mercator) definieras av åtta parametrar. När du anger en Universal Transverse Mercator-projektion för ett terrängbildslager måste dina terrängbildfiler justeras med false (projiceras) norrut mot bildens överkant och false österut till bildens högra del.

Om du vill ange en UTM-projektion för en terrängbildskälla måste du öppna [!DNL Terrain Images.cfg] i en textredigerare som Anteckningar anger du parametern Projection Info till till TransverseMercatorProjection och lägger till inställningar för UTM-projektionen.

**Ange en Universal Transverse Mercator-projektion**

1. I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL Terrain Images.cfg] filen finns i den här katalogen.
1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Terrain Images.cfg]och sedan klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Terrain Images.cfg.]
1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg] -filen visas i ett Anteckningsfönster.
1. Redigera parametrarna för projektionsinformation med följande exempelfilfragment och parametertabell som stödlinjer. Var noga med att specificera projektionstypen så som den markeras nedan.

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ellipsoid Inverse Flattening, Ellipsoid Semimajor Axis </p> </td> 
   <td colname="col2"> <p>Parametrarna för den ellipsoid som används för projektionen. Halvhuvudsaxeln anges i meter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falsk inklistring </p> </td> 
   <td colname="col2"> <p>Falsk estring av projektionens mitterdianer, i meter. För UTM är detta alltid 500 000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falskt Northing </p> </td> 
   <td colname="col2"> <p>Ekvatorns falska norning i projektionen, i meter. För UTM är detta 0 för områden på norra halvklotet och 10 000 för områden på södra halvklotet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Koordinater för nordvästra hörnet, koordinater för sydöstra hörn </p> </td> 
   <td colname="col2"> <p>Koordinaterna (i projicerade meter) för bildens övre vänstra och nedre högra hörn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prime Meridian </p> </td> 
   <td colname="col2"> <p>Longitud för projektionsytans mitterdlinje, angiven i grader öster om Greenwich. Negativa tal kan användas för att ange grader västerut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skalfaktor </p> </td> 
   <td colname="col2"> <p>Projektionscylinderns radie i förhållande till ellipsoidens halvhuvudaxel. För UTM-projektioner (Universal Transverse Mercator) är detta alltid 0,9996. </p> </td> 
  </tr> 
 </tbody> 
</table>
