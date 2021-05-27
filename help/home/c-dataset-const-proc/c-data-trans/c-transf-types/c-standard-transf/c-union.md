---
description: Unionsomformningen tar en uppsättning indata och skapar en vektor med strängar som utdata.
title: Union
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
exl-id: 841b5133-d587-409c-b39e-47169beb2ddf
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---

# Union{#union}

Unionsomformningen tar en uppsättning indata och skapar en vektor med strängar som utdata.

Om en av inmatningarna själv är en vektor, associeras varje element i inmatningsvektorn med ett element i utmatningsvektorn (det vill säga transformeringen skapar inte en vektor för vektorer).

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Standardvärdet som ska användas om villkoret är uppfyllt och indatavärdet inte är tillgängligt. |  |
| Indata | Ett eller flera indatavärden. |  |
| Utdata | Namnet på utdatafältet. |  |

I det här exemplet används datafält från webbplatstrafiken för att skapa en lista med de postnummer som är kopplade till webbplatsens besökare (det vill säga inom varje loggpost). Dessa data kan innehålla två källor: en i cs-uri-query och den andra i ett [!DNL zipcode]-fält i cookien. Om inget av dessa fält innehåller ett postnummer används standardvärdet 0000.

![](assets/cfg_TransformationType_Union.png)

Även om båda dessa värden kan vara tillgängliga i en enda loggpost kan du välja vilket värde som ska användas när du skapar en dimension baserat på omformningens utdata. I vanliga fall skapar du en enkel dimension som tar antingen det första eller det sista av de identifierade värdena. Mer information om hur du skapar enkla dimensioner finns i [Utökade Dimensioner](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
