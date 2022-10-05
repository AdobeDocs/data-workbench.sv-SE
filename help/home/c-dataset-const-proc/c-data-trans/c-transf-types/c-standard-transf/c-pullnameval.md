---
description: DragNameValues-omformningen är en specialåtgärd som tar värdena i cs-uri-query-fältet och separerar varje par av namn/värde till en separat sträng.
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# PullNameValues{#pullnamevalues}

{{eol}}

DragNameValues-omformningen är en specialåtgärd som tar värdena i cs-uri-query-fältet och separerar varje par av namn/värde till en separat sträng.

Hela samlingen med strängar för namnvärdespar skapas i det angivna utdatafältet som en vektor med strängar.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Standardvärdet som ska användas om villkoret är uppfyllt och indatavärdet inte är tillgängligt i den angivna loggposten. |  |
| Utdata | Namnet på utdatasträngen. |  |

The [!DNL PullNameValues] Omvandling används i det här exemplet för att fånga besökarnas användning av sökformuläret: vilka knappar som markerades, vilka värden som skrevs in i formuläret och så vidare. I exemplet används en [!DNL String Match] villkor (se [Villkor](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) för att isolera användningen av den här omformningen till endast sidan [!DNL /search.php]. Vektorn för namn/värde-par skrivs ut i fältet x-search-names.

![](assets/cfg_TransformationType_PullNameValues.png)

Använda omformningen enligt definitionen ovan om cs-uri-stam-fältet matchade sidan [!DNL /search.php] och cs-uri-query innehöll följande:

* SearchFor=Bob&amp;State=Virginia&amp;isMale=true

x-search-namvalues skulle då innehålla en vektor som innehåller följande tre strängar:

* SearchFor=Bob
* State=Virginia
* isMale=true
