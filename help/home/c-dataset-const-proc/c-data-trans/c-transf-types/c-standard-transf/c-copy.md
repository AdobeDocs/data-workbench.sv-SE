---
description: Kopiera-omformningen kopierar bara värdet i indatafältet till det angivna utdatafältet. Om indatafältet kan vara en vektor med strängar måste utdatafältet börja med "x-".
title: Kopiera
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 2%

---

# Kopiera{#copy}

Kopiera-omformningen kopierar bara värdet i indatafältet till det angivna utdatafältet. Om indatafältet kan vara en vektor med strängar måste utdatafältet börja med &quot;x-&quot;.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Används om villkorstestet är true och indatavärdet inte är tillgängligt i den angivna loggposten. |  |
| Indata | Namnet på det fält som du vill kopiera från. |  |
| Utdata | Namnet på utdatafältet. |  |

I det här exemplet, där fält med data som samlats in från webbplatstrafiken används, får utdatafältet x-purchase-success det literala värdet &quot;1&quot; varje gång cs-uri-stam matchar [!DNL /checkout/confirmed.php]. Om [!DNL Condition] inte är nöjd (d.v.s. cs-uri-stammen inte matchar [!DNL /checkout/confirmed.php]) ändras inte x-purchase-success.

![](assets/cfg_TransformationType_Copy.png)
