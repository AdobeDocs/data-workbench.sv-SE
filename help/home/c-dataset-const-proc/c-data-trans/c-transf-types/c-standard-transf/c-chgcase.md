---
description: Transformeringen ChangeCase ändrar skiftläget för strängen i parametern Input enligt parametern Action.
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

Transformeringen ChangeCase ändrar skiftläget för strängen i parametern Input enligt parametern Action.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Åtgärd | Upper eller lägre. Anger om skiftläget ska ändras till över- eller underkant. | nedre |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Indata | Namnet på fältet från loggposten som ska användas som indata. |  |
| Utdata | Namnet på utdatafältet. |  |

I det här exemplet, som använder fält med data som samlats in från webbplatstrafiken, ändras skiftläget för strängen i fältet s-dns till gemener, och det nya värdet skrivs ut i det nya fältet, x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)

