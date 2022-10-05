---
description: Omformningen Förenkla tar en vektor med strängar och mappar varje värde till ett eget fält.
title: Förenkla
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---

# Förenkla{#flatten}

{{eol}}

Omformningen Förenkla tar en vektor med strängar och mappar varje värde till ett eget fält.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Standardvärdet som ska användas om villkoret är uppfyllt och indatavärdet inte är tillgängligt för loggposten. |  |
| Indata | En vektor med strängvärden som ska mappas till utdatafältnamnen. |  |
| Utdata | En uppsättning utdatafältnamn. |  |

Att tänka på [!DNL Flatten]

* Om indatavektorn innehåller fler värden än det finns definierade utdatafält tas de extra indatavärdena bara bort.
* Om indatavektorn innehåller färre värden än det finns definierade utdatafält får de extra utdatafälten standardvärdet (om det är definierat) eller en tom sträng om inget standardvärde är definierat.

Här är [!DNL Flatten] Omvandling används för att ta en vektor med produkter (x-produkter) och dela upp dem i fyra fält (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Om indatavärdet innehöll strängarna B57481, C46355 och Z97123, skulle utdatafälten ha de värden som visas här:

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Tom (Det finns fler indata än utdata och inget standardvärde har angetts.)
