---
description: Omvandlingar och dimensioner använder villkor för att avgöra när vissa instruktioner eller åtgärder gäller för loggfält.
title: Om villkor
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Om villkor{#about-conditions}

Omvandlingar och dimensioner använder villkor för att avgöra när vissa instruktioner eller åtgärder gäller för loggfält.

Parametern Villkor för loggpost använder villkor för att avgöra vilka loggposter som ska inkluderas i datauppsättningsprocessen. I den här bilagan beskrivs de olika typerna av villkor som finns på data workbench-servern.

Ett villkor tillhör en av två kategorier:

* **[!DNL Test Operations]:** [!DNL Compare],  [!DNL Not Empty],  [!DNL Range],  [!DNL Regular Expression]och  [!DNL String Match] villkor används för att testa olika lägen i de tillgängliga loggfälten.

* **[!DNL Boolean Operations]:** Villkoren  [!DNL And],  [!DNL Or]och  [!DNL Neither] används för att kombinera de teståtgärder som beskrivs ovan. Om du till exempel har ett [!DNL Range]-villkor och ett [!DNL String Match]-villkor som båda måste vara false för att kunna utföra rätt åtgärd, gör du dessa två åtgärder underordnade villkoret [!DNL Neither]. Observera att villkoret [!DNL And] används som rot för alla villkorstestningar i systemet.
