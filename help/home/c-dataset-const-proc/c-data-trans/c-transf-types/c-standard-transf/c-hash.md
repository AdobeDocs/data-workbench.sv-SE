---
description: Hash-omformningen skapar en nästan unik sträng som representerar ett 64-bitars tal från indatavärdena.
solution: Analytics
title: Hash
topic: Data workbench
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hash{#hash}

Hash-omformningen skapar en nästan unik sträng som representerar ett 64-bitars tal från indatavärdena.

Den här omformningen ger samma hash-värde när samma indata anges.

>[!NOTE]
>
>Resultatvärdet är nästan unikt eftersom omformningen använder ett 64-bitars tal som utrymme för möjliga hash-värden. För en miljon unika indata i [!DNL hash] omvandlingen finns det en chans på 38 000 000 att få ett duplicerat hash-värde.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Standardvärdet som ska användas om indatavärdet inte är tillgängligt. |  |
| Indata | Den uppsättning indata som ska användas för att skapa hash-värdet. |  |
| Utdata | Namnet på fältet för utdata. |  |

I det här exemplet används värdena i fälten c-ip och cs(user-agent) för att skapa ett spårnings-ID, som lagras i fältet x-trackingid.

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Det här exemplet är inte en idealisk lösning för att skapa unika spårnings-ID:n. I situationer där arkivlogginformation används kan det dock vara den bästa metoden.

