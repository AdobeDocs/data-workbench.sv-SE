---
description: UTM-projektionen (Universal Transverse Mercator) definieras av åtta parametrar.
title: Universal Transverse Mercator Projection
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---

# Universal Transverse Mercator Projection{#universal-transverse-mercator-projections}

{{eol}}

UTM-projektionen (Universal Transverse Mercator) definieras av åtta parametrar.

När du anger en Universal Transverse Mercator-projektion för ett terrängbildslager måste dina terrängbildfiler justeras med false (projiceras) norrut mot bildens överkant och false österut till bildens högra del.

Om du vill ange en UTM-projektion för en terrängbildskälla måste du öppna [!DNL Terrain Images.cfg] i en textredigerare som Anteckningar anger du parametern Projection Info till till TransverseMercatorProjection och lägger till inställningar för UTM-projektionen.

**Ange en Universal Transverse Mercator-projektion**

1. I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL Terrain Images.cfg] filen finns i den här katalogen.

1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn för [!DNL Terrain Images.cfg]och sedan klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Terrain Images.cfg].

1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg]-filen visas i ett Anteckningsfönster.

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

| Parameter | Beskrivning |
|---|---|
| Ellipsoid Inverse Flattening, Ellipsoid Semimajor Axis | Parametrarna för den ellipsoid som används för projektionen. Halvhuvudsaxeln anges i meter. |
| Falsk inklistring | Falsk estring av projektionens mitterdianer, i meter. För UTM är detta alltid 500 000. |
| Falskt Northing | Ekvatorns falska norning i projektionen, i meter. För UTM är detta 0 för områden på norra halvklotet och 10 000 för områden på södra halvklotet. |
| Koordinater för nordvästra hörnet, koordinater för sydöstra hörn | Koordinaterna (i projicerade meter) för bildens övre vänstra och nedre högra hörn. |
| Prime Meridian | Longitud för projektionsytans mitterdlinje, angiven i grader öster om Greenwich. Negativa tal kan användas för att ange grader västerut. |
| Skalfaktor | Projektionscylinderns radie i förhållande till ellipsoidens halvhuvudaxel. För UTM-projektioner (Universal Transverse Mercator) är detta alltid 0,9996. |
