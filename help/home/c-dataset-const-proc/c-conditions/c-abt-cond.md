---
description: Omvandlingar och dimensioner använder villkor för att avgöra när vissa instruktioner eller åtgärder gäller för loggfält.
solution: Analytics
title: Om villkor
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Om villkor{#about-conditions}

Omvandlingar och dimensioner använder villkor för att avgöra när vissa instruktioner eller åtgärder gäller för loggfält.

Parametern Villkor för loggpost använder villkor för att avgöra vilka loggposter som ska inkluderas i datauppsättningsprocessen. I den här bilagan beskrivs de olika typerna av villkor som finns på data workbench-servern.

Ett villkor tillhör en av två kategorier:

* **[!DNL Test Operations]:**[!DNL Compare],[!DNL Not Empty],[!DNL Range],[!DNL Regular Expression]och[!DNL String Match]villkor används för att testa olika lägen i de tillgängliga loggfälten.

* **[!DNL Boolean Operations]:**Villkoren[!DNL And],[!DNL Or]och[!DNL Neither]används för att kombinera de provningsåtgärder som beskrivs ovan. Om du till exempel har ett[!DNL Range]villkor och ett[!DNL String Match]villkor som måste vara false för att kunna utföra rätt åtgärd, gör du dessa två åtgärder underordnade[!DNL Neither]villkoret. Observera att[!DNL And]villkoret används som rot för alla villkorstestningar i systemet.

