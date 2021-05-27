---
description: Konceptuell information om arbetsytor och visualiseringar.
title: Arbetsytor och visualiseringar
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Arbetsytor och visualiseringar{#workspaces-and-visualizations}

Konceptuell information om arbetsytor och visualiseringar.

I bilden nedan visas en beroendekarta vars noder representerar de arbetsytor, rapporter, menyalternativ och globala lager som definierats i profilen. Det här alternativet fungerar bara om visningsalternativet [!DNL Query Model] är aktiverat.

>[!NOTE]
>
>Om visningsalternativet [!DNL Query Model] inte är aktiverat när du väljer visningsalternativet [!DNL Workspaces and Visualizations] visas ett felmeddelande.

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* En grå nod representerar en arbetsyta eller en rapport.
* En gulgrön nod representerar ett menyalternativ.
* En röd nod representerar en arbetsyta, en rapport, ett menyalternativ eller ett globalt lager med ett brutet eller cirkulärt beroende eller något annat fel.

>[!NOTE]
>
>Eftersom beroendekartan är utformad för att rymma acykliska beroenden, kanske noder som är inblandade i cirkulära beroenden inte visas korrekt på kartan. Du kan söka efter cirkulära beroenden genom att skriva &quot;cirkelberoende&quot; i textrutan [!DNL Search]. Mer information om funktionen [!DNL Search] finns i [Söka i en karta](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

Beskrivningar av andra noder på kartan finns i [Frågemodellkomponenter](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
