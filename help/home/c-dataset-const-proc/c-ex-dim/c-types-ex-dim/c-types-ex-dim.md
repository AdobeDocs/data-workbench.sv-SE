---
description: Med Insight Server kan du definiera räkneliga, enkla, många-till-många, numeriska, denorala och tidsmässiga dimensioner som ska ingå i datauppsättningen.
title: Typer av utökade Dimensioner
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Typer av utökade Dimensioner{#types-of-extended-dimensions}

{{eol}}

Med Insight Server kan du definiera räkneliga, enkla, många-till-många, numeriska, denorala och tidsmässiga dimensioner som ska ingå i datauppsättningen.

Varje dimensionstyp har en uppsättning parametrar vars värden du redigerar för att ge specifika instruktioner för Insight Server att skapa dimensionerna under datauppsättningens omformningsfas.

Vissa parametrar skiljer sig åt mellan olika dimensionstyper, men alla kräver en specifikation av en överordnad dimension (parametern Parent). Den överordnade dimensionen avgör vilka loggposter från loggkällorna som anges som indata till den nya dimensionen. Loggposterna som är kopplade till elementen i den överordnade dimensionen är alltså de som är kopplade till den nya dimensionen innan någon filtrering tillämpas. Den överordnade dimensionen avgör också den nya dimensionens position i datauppsättningens hierarki, som kallas datauppsättningsschema. Mer information om gränssnittet som visar datauppsättningsschemat finns i [Verktyg för datauppsättningskonfiguration](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

När Insight Server använder den överordnade dimensionen för att avgöra vilka loggposter som ska beaktas när dimensionen skapas, används de angivna villkoren (parametern Condition) för att tömma de loggposter som inte uppfyller villkoret. Servern identifierar sedan värdet för det angivna indatafältet (parametern Input) för varje loggpost och tillämpar den angivna åtgärden (parametern Operation), om tillämpligt.

>[!NOTE]
>
>Om en loggpost inte uppfyller villkoren för en utökad dimension ersätter Insight Server tomma värden för alla fält i loggposten. Den faktiska loggposten finns fortfarande och den angivna åtgärden avgör om det tomma värdet för [!DNL Input] fältet används.
