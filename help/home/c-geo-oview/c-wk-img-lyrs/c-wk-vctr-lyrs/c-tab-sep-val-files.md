---
description: När du skapar ett vektorlager som refererar till en tabbseparerad värdefil (.tsv), hämtas vektordata genom att både ritinstruktioner och longitud- och latituddata hämtas från .tsv-filen.
title: Vektorlager som refererar till filer med tabbseparerade värden
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Vektorlager som refererar till filer med tabbseparerade värden{#vector-layers-referencing-tab-separated-values-files}

{{eol}}

När du skapar ett vektorlager som refererar till en tabbseparerad värdefil (.tsv), hämtas vektordata genom att både ritinstruktioner och longitud- och latituddata hämtas från .tsv-filen.

Definiera ett vektorlager som refererar till ett [!DNL .tsv] -filer måste du ha följande:

* **A [!DNL .tsv] fil** som innehåller de data som används för att rita vektorerna på jorden, inklusive longitud- och latituddata. Mer information om vilket format som krävs för [!DNL .tsv] -fil, se [Vector TSV-filformat](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **En lagerfil** som anger platsen för [!DNL .tsv] -fil. Mer information om vilket format lagerfilen ska ha finns i [Vektorlagerfilformat](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Vector TSV, filformat {#section-a29012c9ff4444ac8a6d41c68482828e}

The [!DNL .tsv] filen måste innehålla följande tre tabbavgränsade kolumner:

* **[!DNL Begin]:** Den här kolumnen ska ange om en ny rad ska börja. Värdena i den här kolumnen kan vara 0 (börja inte en ny rad) eller 1 (börja en ny rad).
* **[!DNL Longitude]:** Den här kolumnen ska innehålla longitudvärden.
* **[!DNL Latitude]:** Den här kolumnen ska innehålla latitudvärden.

>[!NOTE]
>
>Eventuella ytterligare kolumner ignoreras.

Här följer ett exempel [!DNL .tsv] fil som innehåller data för ett vektorlager:

![](assets/tsv_vectorlayer.png)

## Filformat för vektorlager {#section-c430923f341f4c93852e9f24b61e82bf}

Varje vektorlagerfil som refererar till [!DNL .tsv] filer måste formateras med följande mall:

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> TSV-filer </td> 
   <td colname="col2"> <p>Sökvägar till <span class="filepath"> .tsv</span> filer som innehåller vektordata. </p> <p>Exempel: <span class="filepath"> Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Färg </td> 
   <td colname="col2"> Färgvektorn RGB, som uttrycks som (röd, grön, blå). För varje färg i vektorn kan du ange ett värde mellan 0,0 och 1,0. (1.0, 0.0, 0.0) är till exempel ljusröd och (0.5, 0.5, 0.5) är grå. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alfa </td> 
   <td colname="col2"> Styr genomskinligheten för vektorerna som visas på jorden. Intervallet är 0 till 1, där 0 är det mest genomskinliga. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bredd </td> 
   <td colname="col2"> Valfritt. Anger datans bredd i pixlar. Rekommenderat intervall är 1 till 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felfaktor </td> 
   <td colname="col2"> Styr hur exakt vektorerna ritas. För större värden ritas vektorerna mindre exakt men snabbare. Standardvärdet är 5. </td> 
  </tr> 
 </tbody> 
</table>
