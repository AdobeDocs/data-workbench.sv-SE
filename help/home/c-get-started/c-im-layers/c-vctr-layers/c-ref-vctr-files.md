---
description: Du kan skapa ett vektorlager som refererar till en eller flera vektorfiler (.vec), som innehåller data som definierar vektorerna som ska ritas på jorden.
title: Definiera vektorlager som refererar till vektorfiler
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Definiera vektorlager som refererar till vektorfiler{#define-vector-layers-referencing-vector-files}

Du kan skapa ett vektorlager som refererar till en eller flera vektorfiler (.vec), som innehåller data som definierar vektorerna som ska ritas på jorden.

Om du vill definiera ett vektorlager som refererar till en eller flera [!DNL .vec]-filer måste du ha följande:

* **En eller flera  [!DNL .vec]** filer som innehåller de data som används för att rita vektorerna på jorden.

   >[!NOTE]
   >
   >Om du vill få [!DNL .vec]-filer att använda med dina vektorlager kontaktar du Adobe.

* **En lagerfil** som anger platsen för  [!DNL .vec] filerna. Mer information om vilket format lagerfilen ska ha finns i [Vektorlagerfilformat](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1).

   >[!NOTE]
   >
   >Filen [!DNL Boundaries.layer], som ingår i profilen [!DNL Geography], är ett vektorlager som refererar till filerna [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec] och [!DNL mwisland.vec].

## Vektorlagerfilformat {#section-83a0077cf0c8479b9e7b2939bc761af1}

Varje vektorlagerfil som refererar till [!DNL .vec]-filer måste formateras med följande mall:

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
| Vec-filer | Sökväg(er) till [!DNL .vec]-filen/filerna som innehåller vektordata. |
| Färg | RGB-färgvektorn, som uttrycks som (röd, grön, blå). För varje färg i vektorn kan du ange ett värde mellan 0,0 och 1,0. (1.0, 0.0, 0.0) är till exempel ljusröd och (0.5, 0.5, 0.5) är grå. |
| Alfa | Styr genomskinligheten för vektorerna som visas på jorden. Intervallet är 0 till 1, där 0 är det mest genomskinliga. |
| Bredd | Valfritt. Anger datans bredd i pixlar. Rekommenderat intervall är 1 till 4. |
| Felfaktor | Styr hur exakt vektorerna ritas. För större värden ritas vektorerna mindre exakt men snabbare. Standardvärdet är 5. |

Filen [!DNL Boundaries.layer] har följande format:

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
