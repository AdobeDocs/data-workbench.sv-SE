---
description: URI-omformningen Unescape tar bort alla tecken i en sträng som har escape-konverterats.
title: UnescapeURI
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
exl-id: abf20906-5052-4bbe-9ffb-522b850669a6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 2%

---

# UnescapeURI{#unescapeuri}

URI-omformningen Unescape tar bort alla tecken i en sträng som har escape-konverterats.

>[!NOTE]
>
>Escaped-tecken ersätter osäkra tecken i en URI-sträng. De representeras av en triplet som består av ett procenttecken följt av två hexadecimala siffror (till exempel %20).

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Standardvärdet som ska användas om villkoret är uppfyllt och indatavärdet inte är tillgängligt. |  |
| Indata | Den URI-sträng som ska unescape-konverteras. |  |
| Utdata | Namnet på det fält där den unescape-konverterade strängen ska lagras. |  |

Följande omformning tar bort inseendet på dokumentnamnsvärdet i ett HTTP-rubrikfält och lagrar utdata i fältet x-docname-unescape:

![](assets/cfg_TransformationType_UnescapeURI.png)

Om dokumentnamnsvärdet var

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

blir värdet för x-docname-unescape

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]
