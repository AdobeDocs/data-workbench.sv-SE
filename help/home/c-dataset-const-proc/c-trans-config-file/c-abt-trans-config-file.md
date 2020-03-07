---
description: Filen Transformation.cfg styr omformningsfasen för datauppsättningens konstruktion under vilken ytterligare dataomformningar tillämpas på data som redan bearbetats under loggbearbetningen för att skapa utökade dimensioner som kan användas i analysen.
solution: Analytics
title: Om Transformation Configuration File
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Om Transformation Configuration File{#about-the-transformation-configuration-file}

Filen Transformation.cfg styr omformningsfasen för datauppsättningens konstruktion under vilken ytterligare dataomformningar tillämpas på data som redan bearbetats under loggbearbetningen för att skapa utökade dimensioner som kan användas i analysen.

Du måste redigera [!DNL Transformation.cfg] filen för att kunna utföra följande datauppsättningskonfigurationsåtgärder:

* Filtrera data från loggbearbetning genom att definiera omformningsmetoden [!DNL log entry condition] .
* Anger den tidszon som ska användas för att skapa tidsdimensioner och göra tidskonverteringar. Se [Tidszoner](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] -filer kan innehålla ytterligare instruktioner för omformningsfasen för datauppsättningens konstruktion. Dessa filer finns i katalogen DataSet\Transformation för alla ärvda profiler, och de definierar vanligtvis programspecifika parametrar (till exempel webbspecifika konfigurationsparametrar för [!DNL Site] programmet). Mer information om [!DNL Transformation Dataset Include] filer finns i [Inkludera filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)i datauppsättning. Mer information om webbspecifika konfigurationsparametrar för platsen finns i [Konfigurationsinställningar för webbdata](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

