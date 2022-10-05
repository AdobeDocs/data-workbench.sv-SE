---
description: Latitud-longitud-projektionsformatet (LatLonProjection) i filen Terrain Images.cfg definieras av fyra parametrar för latitud och longitud.
title: Latitude-longitud - prognoser
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 1%

---

# Latitude-longitud - prognoser{#latitude-longitude-projections}

{{eol}}

Latitud-longitud-projektionsformatet (LatLonProjection) i filen Terrain Images.cfg definieras av fyra parametrar för latitud och longitud.

Om du vill ange en LatLonProjection för oprojicerade bilder (oprojicerade råbilder och allmänna bilder, oprojicerade) kan du ange inställningar för LatLonProjection i [!DNL Terrain Images.cfg] i data workbench. Se [Ange en LatLonProjection för oprojicerade bilder](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

Om du vill ange en LatLonProjection för bilder med inbäddad projektionsinformation måste du öppna [!DNL Terrain Images.cfg] i en textredigerare som Anteckningar anger du parametern Projection Info till till &quot;LatLonProjection&quot; och lägger till inställningar för LatLonProjection. Se [Om du vill ange en LatLonProjection för bilder i inbäddad projektionsinformation...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [Ange en LatLonProjection för oprojicerade bilder](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [Om du vill ange en LatLonProjection för bilder inom inbäddad projektionsinformation...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## Ange en LatLonProjection för oprojicerade bilder {#section-26554eefe645481faba68396fa13756a}

1. Öppna [!DNL Terrain Images.cfg] i data workbench och lägga till en terrängbildlagerkälla enligt beskrivningen i [Definiera ett terrängbildlager](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. Redigera parametrarna för Projektionsinformation med följande parametertabell som vägledning:

   | Parameter | Beskrivning |
   |---|---|
   | Lat0 | Latituden på bildens överkant, i grader, där 90 är Nordpolen och -90 är Sydpolen. |
   | Lat1 | Latitud för bildens nederkant. |
   | Lon0 | Longitud för bildens vänstra kant, i grader, där positiva tal är öster och negativa tal är longituder väster. |
   | Lon1 | Longitud för bildens högra kant. |

1. Spara filen genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

1. Om du vill spara de lokalt gjorda ändringarna i data workbench-serverdatorn går du till [!DNL Server Files Manager], högerklicka på bockmarkeringen för [!DNL Terrain Images.cfg] i [!DNL Temp] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Ange en LatLonProjection för bilder inom inbäddad projektionsinformation {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL Terrain Images.cfg] filen finns i den här katalogen.

1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Terrain Images.cfg]och sedan klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Terrain Images.cfg].

1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg] -filen visas i ett Anteckningsfönster.

1. Redigera parametrarna för projektionsinformation med följande exempelfilfragment som hjälp. Var noga med att specificera projektionstypen så som den markeras nedan. Beskrivningar av parametrarna finns i tabellen LatLonProjection Parameters i föregående procedur.

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
