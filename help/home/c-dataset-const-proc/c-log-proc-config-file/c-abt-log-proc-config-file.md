---
description: Filen Log Processing.cfg styr loggbearbetningsfasen för datauppsättningen, under vilken oordnade data läses från datakällorna (kallas loggkällor) och filter och omformningar tillämpas på data.
title: Om konfigurationsfilen för loggbearbetning
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Om konfigurationsfilen för loggbearbetning{#about-the-log-processing-configuration-file}

{{eol}}

Filen Log Processing.cfg styr loggbearbetningsfasen för datauppsättningen, under vilken oordnade data läses från datakällorna (kallas loggkällor) och filter och omformningar tillämpas på data.

Du måste redigera [!DNL Log Processing.cfg] om du vill utföra någon av följande datauppsättningskonfigurationsåtgärder:

* Ange loggkällor. Se [Loggkällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Avgör vilka loggposter som anger datauppsättningen under loggbearbetningen. Se [Datafilter](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) och [Loggpostvillkor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Möjliggör delning av spårnings-ID:n med stora mängder händelsedata. Se [Nyckeldelning](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Konfigurerar en data workbench-server som ska köras som en filserverenhet. Se [Konfigurera en filserverenhet för Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* Konfigurera en data workbench-server som ska köras som en centraliserad normaliseringsserver. Se [Konfigurera en filserverenhet för Insight Server](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] filer kan innehålla ytterligare instruktioner för loggbearbetningsfasen för datauppsättningens konstruktion. Dessa filer finns i katalogen DataSet\Log Processing för alla ärvda profiler. De definierar vanligtvis programspecifika parametrar (till exempel webbspecifika konfigurationsparametrar för platsprogrammet). Mer information om [!DNL Log Processing Dataset Include] filer, se [Datauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Mer information om webbspecifika konfigurationsparametrar för platsen finns i [Konfigurationsinställningar för webbdata](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
