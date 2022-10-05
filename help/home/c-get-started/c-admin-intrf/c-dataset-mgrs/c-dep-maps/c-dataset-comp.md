---
description: Konceptuell information om datauppsättningskomponenter.
title: Datauppsättningskomponenter
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Datauppsättningskomponenter{#dataset-components}

{{eol}}

Konceptuell information om datauppsättningskomponenter.

I bilden nedan visas en beroendekarta vars noder representerar en datamängds loggkällor, fält, omformningar och utökade dimensioner.

![](assets/vis_DependencyMap.png)

* En gulgrön nod representerar en eller flera loggkällor eller ett filter (till exempel ett villkor för loggpost) som definieras i datauppsättningen.

   * En nod för en loggkälla visas alltid längst till vänster på kartan. Om datauppsättningen har en enda loggkälla visas loggkällan på kartan: *loggkällans namn*. Om datauppsättningen har flera loggkällor visas kartan *tal* Loggkällor, där antal är antalet loggkällor. Om du t.ex. har tre loggkällor i datauppsättningen visas 3 loggkällor på kartan.

   * På kartan visas en nod för villkor för loggpost för varje [!DNL log processing dataset include] fil men bara en villkorsnod för loggpost för omvandling (om den har definierats i [!DNL Transformation.cfg] fil). Om villkoret för loggpost är tomt visas det inte på kartan.

* En grå nod representerar ett fält som listas i parametern Fält i en [!DNL Log Processing.cfg] eller [!DNL Log Processing include] -fil.

* En blå nod representerar en omformning.
* En grön nod representerar en utökad dimension.

>[!NOTE]
>
>Om mappen DataSet i din profil innehåller filen [!DNL Insight Transform.cfg]I beroendekartan visas loggkällor, omformningar och exporterare som definierats för Transform. Mer information om Omforma finns i *Konfigurationshandbok för datauppsättning*.

När du aktiverar alternativet Inkludera [!DNL File Blocks] visningsalternativet visar kartan en enda blå nod för alla omformningar som definieras i en datauppsättningskonfigurationsfil och en enda grön nod för alla utökade dimensioner som definieras i en datauppsättningskonfigurationsfil. Mer information om det här visningsalternativet finns i [Arbeta med filblock](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
