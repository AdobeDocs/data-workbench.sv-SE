---
description: Latitud-longitud-projektionsformatet (LatLonProjection) i filen Terrain Images.cfg definieras av fyra parametrar för latitud och longitud.
solution: Analytics
title: Latitude-longitud - prognoser
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Latitude-longitud - prognoser{#latitude-longitude-projections}

Latitud-longitud-projektionsformatet (LatLonProjection) i filen Terrain Images.cfg definieras av fyra parametrar för latitud och longitud.

Om du vill ange en LatLonProjection för oprojicerade bilder (oprojicerade råbilder och allmänna bilder, oprojicerade) kan du ange inställningar för LatLonProjection i fönstret i [!DNL Terrain Images.cfg] data workbench. Se [Ange en LatLonProjection för oprojicerade bilder](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

Om du vill ange en LatLonProjection för bilder med inbäddad projektionsinformation, måste du öppna [!DNL Terrain Images.cfg] filen i en textredigerare som Anteckningar, ange parametern Projection Info till &quot;LatLonProjection&quot; och lägga till inställningar för LatLonProjection. Se [Ange en LatLonProjection för bilder i inbäddad projektionsinformation...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Ange en LatLonProjection för oprojicerade bilder](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Om du vill ange en LatLonProjection för bilder inom inbäddad projektionsinformation...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Ange en LatLonProjection för oprojicerade bilder {#section-26554eefe645481faba68396fa13756a}

1. Öppna [!DNL Terrain Images.cfg] filen i data workbench och lägg till en källfil för terrängbildlager enligt beskrivningen i [Definiera ett terrängbildlager](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. Redigera parametrarna för Projektionsinformation med följande parametertabell som vägledning:

   | Parameter | Beskrivning |
   |---|---|
   | Lat0 | Latituden på bildens överkant, i grader, där 90 är Nordpolen och -90 är Sydpolen. |
   | Lat1 | Latitud för bildens nederkant. |
   | Lon0 | Longitud för bildens vänstra kant, i grader, där positiva tal är öster och negativa tal är longituder väster. |
   | Lon1 | Longitud för bildens högra kant. |

1. Spara filen genom att högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

1. Om du vill spara de lokalt gjorda ändringarna i data workbench-serverdatorn högerklickar du i [!DNL Server Files Manager]kryssrutan för [!DNL Terrain Images.cfg] i [!DNL Temp] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Ange en LatLonProjection för bilder inom inbäddad projektionsinformation {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL Terrain Images.cfg] katalogen.

1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Terrain Images.cfg]och klicka sedan på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Terrain Images.cfg].

1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Filen visas i ett fönster med Anteckningar [!DNL Terrain Images.cfg] .

1. Redigera parametrarna för projektionsinformation med följande exempelfilfragment som hjälp. Var noga med att specificera projektionstypen så som den markeras nedan. Beskrivningar av parametrarna finns i tabellen LatLonProjection Parameters i föregående procedur.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

