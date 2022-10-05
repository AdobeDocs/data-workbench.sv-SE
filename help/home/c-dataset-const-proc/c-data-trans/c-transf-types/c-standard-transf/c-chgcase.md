---
description: Transformeringen ChangeCase ändrar skiftläget för strängen i parametern Input enligt parametern Action.
title: ChangeCase
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
exl-id: 2002fe22-d31c-4286-9f73-59ef205f1384
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 2%

---

# ChangeCase{#changecase}

{{eol}}

Transformeringen ChangeCase ändrar skiftläget för strängen i parametern Input enligt parametern Action.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Åtgärd | Upper eller lägre. Anger om skiftläget ska ändras till över- eller underkant. | nedre |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Indata | Namnet på fältet från loggposten som ska användas som indata. |  |
| Utdata | Namnet på utdatafältet. |  |

I det här exemplet, där fält med data som samlats in från webbplatstrafiken används, ändras strängens skiftläge i fältet s-dns till gemener, och det nya värdet skrivs ut i det nya fältet, x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)
