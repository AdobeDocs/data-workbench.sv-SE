---
description: Du kan skapa ett vektorlager som refererar till en eller flera vektorfiler (.vec), som innehåller data som definierar vektorerna som ska ritas på jorden.
title: Definiera vektorlager som refererar till vektorfiler
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
exl-id: c6da3cd9-f42a-4e9c-ae48-9f4ffdc42f7b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Definiera vektorlager som refererar till vektorfiler{#defining-vector-layers-referencing-vector-files}

{{eol}}

Du kan skapa ett vektorlager som refererar till en eller flera vektorfiler (.vec), som innehåller data som definierar vektorerna som ska ritas på jorden.

Definiera ett vektorlager som refererar till ett eller flera lager [!DNL .vec]-filer måste du ha följande:

* En eller flera [!DNL .vec]filer som innehåller de data som används för att rita vektorerna på jorden.

   >[!NOTE]
   >
   >För att få [!DNL .vec] ska du kontakta Adobe.

* En lagerfil som anger platsen för [!DNL .vec] filer. Mer information om vilket format lagerfilen ska ha finns i [Vektorlagerfilformat](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a).

   >[!NOTE]
   >
   >The [!DNL Boundaries.layer] fil, som tillhandahålls med [!DNL Geography] profil, är ett vektorlager som refererar till [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]och [!DNL mwisland.vec] filer.

## Vektorlagerfilformat {#section-530d03f41ede4a339aebbb680e15240a}

Varje vektorlagerfil som refererar till [!DNL .vec]filer måste formateras med följande mall:

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| Parameter | Beskrivning |
|---|---|
| Vec-filer | Sökvägar till [!DNL .vec] filer som innehåller vektordata. |
| Färg | Färgvektorn RGB, som uttrycks som (röd, grön, blå). För varje färg i vektorn kan du ange ett värde mellan 0,0 och 1,0. (1.0, 0.0, 0.0) är till exempel ljusröd och (0.5, 0.5, 0.5) är grå. |
| Alfa | Styr genomskinligheten för vektorerna som visas på jorden. Intervallet är 0 till 1, där 0 är det mest genomskinliga. |
| Bredd | Valfritt. Anger datans bredd i pixlar. Rekommenderat intervall är 1 till 4. |
| Felfaktor | Styr hur exakt vektorerna ritas. För större värden ritas vektorerna mindre exakt men snabbare. Standardvärdet är 5. |

The [!DNL Boundaries.layer] filen har följande format:

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```
