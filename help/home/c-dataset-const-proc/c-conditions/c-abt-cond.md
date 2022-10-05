---
description: Omvandlingar och dimensioner använder villkor för att avgöra när vissa instruktioner eller åtgärder gäller för loggfält.
title: Om villkor
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Om villkor{#about-conditions}

{{eol}}

Omvandlingar och dimensioner använder villkor för att avgöra när vissa instruktioner eller åtgärder gäller för loggfält.

Parametern Villkor för loggpost använder villkor för att avgöra vilka loggposter som ska inkluderas i datauppsättningsprocessen. I den här bilagan beskrivs de olika typerna av villkor som finns på data workbench-servern.

Ett villkor tillhör en av två kategorier:

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression]och [!DNL String Match] villkor används för att testa olika lägen i de tillgängliga loggfälten.

* **[!DNL Boolean Operations]:** The [!DNL And], [!DNL Or]och [!DNL Neither] villkor används för att kombinera de provningsåtgärder som beskrivs ovan. Om du till exempel har en [!DNL Range] villkor och [!DNL String Match] om båda måste vara falska för att kunna utföra rätt åtgärd, gör du dessa två åtgärder underordnade [!DNL Neither] villkor. Observera att [!DNL And] -villkoret används som rot för alla villkorstestningar i systemet.
