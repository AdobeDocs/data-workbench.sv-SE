---
description: Konceptuell information om datauppsättningskomponenter.
solution: Analytics
title: Datauppsättningskomponenter
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Datauppsättningskomponenter{#dataset-components}

Konceptuell information om datauppsättningskomponenter.

I bilden nedan visas en beroendekarta vars noder representerar en datamängds loggkällor, fält, omformningar och utökade dimensioner.

![](assets/vis_DependencyMap.png)

* En gulgrön nod representerar en eller flera loggkällor eller ett filter (till exempel ett villkor för loggpost) som definieras i datauppsättningen.

   * En nod för en loggkälla visas alltid längst till vänster på kartan. Om datauppsättningen har en enda loggkälla visas loggkällan på kartan: *loggkällans namn*. Om datauppsättningen har flera loggkällor visas *antal* loggkällor på kartan, där antal är antalet loggkällor. Om du t.ex. har tre loggkällor i datauppsättningen visas 3 loggkällor på kartan.

   * På kartan visas en nod för Loggpostvillkor för varje [!DNL log processing dataset include] fil, men bara en nod för Loggpostvillkor för omformning (om den har definierats i [!DNL Transformation.cfg] filen). Om villkoret för loggpost är tomt visas det inte på kartan.

* En grå nod representerar ett fält som listas i parametern Fält i en [!DNL Log Processing.cfg] eller [!DNL Log Processing include] fil.

* En blå nod representerar en omformning.
* En grön nod representerar en utökad dimension.

>[!NOTE]
>
>Om mappen DataSet i din profil innehåller filen [!DNL Insight Transform.cfg]visas loggkällor, omformningar och exporterare som definierats för användning med Transform. Mer information om omformning finns i *konfigurationsguiden* för datauppsättningar.

När du aktiverar alternativet Inkludera [!DNL File Blocks] visas en blå nod för alla omformningar som definieras i en datauppsättningskonfigurationsfil och en grön nod för alla utökade dimensioner som definieras i en datauppsättningskonfigurationsfil. Mer information om det här visningsalternativet finns i [Arbeta med filblock](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
