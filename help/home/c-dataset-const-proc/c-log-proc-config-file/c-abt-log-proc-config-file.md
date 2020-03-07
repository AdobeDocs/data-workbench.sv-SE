---
description: Filen Log Processing.cfg styr loggbearbetningsfasen för datauppsättningen, under vilken oordnade data läses från datakällorna (kallas loggkällor) och filter och omformningar tillämpas på data.
solution: Analytics
title: Om konfigurationsfilen för loggbearbetning
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Om konfigurationsfilen för loggbearbetning{#about-the-log-processing-configuration-file}

Filen Log Processing.cfg styr loggbearbetningsfasen för datauppsättningen, under vilken oordnade data läses från datakällorna (kallas loggkällor) och filter och omformningar tillämpas på data.

Du måste redigera [!DNL Log Processing.cfg] filen för att kunna utföra följande datauppsättningskonfigurationsåtgärder:

* Ange loggkällor. Se [Loggkällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* Avgör vilka loggposter som anger datauppsättningen under loggbearbetningen. Se [Datafilter](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) och [Loggpostvillkor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* Möjliggör delning av spårnings-ID:n med stora mängder händelsedata. Se [Nyckeldelning](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* Konfigurerar en data workbench-server som ska köras som en filserverenhet. Se [Konfigurera en filserverenhet](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)för Insight Server.
* Konfigurera en data workbench-server som ska köras som en centraliserad normaliseringsserver. Se [Konfigurera en filserverenhet](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)för Insight Server.

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] filer kan innehålla ytterligare instruktioner för loggbearbetningsfasen för datauppsättningens konstruktion. Dessa filer finns i katalogen DataSet\Log Processing för alla ärvda profiler. De definierar vanligtvis programspecifika parametrar (till exempel webbspecifika konfigurationsparametrar för platsprogrammet). Mer information om [!DNL Log Processing Dataset Include] filer finns i [Inkludera filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)i datauppsättning. Mer information om webbspecifika konfigurationsparametrar för platsen finns i [Konfigurationsinställningar för webbdata](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).

