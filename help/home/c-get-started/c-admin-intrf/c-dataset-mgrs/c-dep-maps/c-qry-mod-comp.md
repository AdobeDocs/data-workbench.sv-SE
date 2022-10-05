---
description: Konceptuell information om frågemodellkomponenter.
title: Frågemodellkomponenter
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Frågemodellkomponenter{#query-model-components}

{{eol}}

Konceptuell information om frågemodellkomponenter.

I bilden nedan visas en beroendekarta vars noder representerar en frågemodells mått, härledda mått och filter som definieras i mapparna Dimensioner, Metrisk och Filter i profilen samt de utökade dimensioner som definierats i datauppsättningen och som relaterar till dem på något sätt.

![](assets/vis_DependencyMap_QueryModel.png)

* En gulgrön nod representerar ett filter.
* En lila nod representerar ett mätvärde.
* En blågrön nod representerar en härledd dimension.
* En grön nod representerar en utökad dimension (definieras i datauppsättningen).
* En röd nod representerar ett mått, en härledd dimension eller ett filter med ett brutet eller cirkelberoende eller något annat fel.

>[!NOTE]
>
>Eftersom beroendekartan är utformad för att rymma acykliska beroenden, kanske noder som är inblandade i cirkulära beroenden inte visas korrekt på kartan. Du kan söka efter cirkulära beroenden genom att skriva &quot;cirkelberoende&quot; i dialogrutan [!DNL Search] textruta. Mer information om [!DNL Search] funktion, se [Söka inom en karta](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
