---
description: Många av de interna profiler som du har fått med ditt Adobe-program har egna konfigurationsfiler för datauppsättningar.
solution: Analytics
title: Om Inkludera datauppsättningar
topic: Data workbench
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Om Inkludera datauppsättningar{#about-dataset-include-files}

Många av de interna profiler som du har fått med ditt Adobe-program har egna konfigurationsfiler för datauppsättningar.

Eftersom de interna profilerna är underprofiler till datauppsättningsprofilen innehåller deras datauppsättningskonfigurationsfiler regler som tillhandahåller ytterligare parametrar för loggbehandlings- eller transformeringsfaserna i datauppsättningskonstruktionen. Datauppsättningskonfigurationsfilerna för interna profiler och för eventuella ärvda profiler som du skapar kallas datauppsättningsfiler.

En datauppsättningsfil innehåller en delmängd av parametrarna som finns i huvuddatauppsättningens konfigurationsfiler ( [!DNL Log Processing.cfg] eller [!DNL Transformation.cfg]) för datauppsättningsprofilen. Datauppsättningen innehåller filer som innehåller parametrar som är associerade med loggbearbetning som kallas [!DNL Log Processing Dataset Include] filer (se [Inkludera filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)i Loggbearbetning av datauppsättning), medan datauppsättningar som innehåller filer som är associerade med omvandling kallas [!DNL Transformation Dataset Include] Filer. Se [Omvandlingsdatauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Du kan skapa flera datauppsättningar med filer som ska användas i datauppsättningsprocessen. Den fullständiga datauppsättningen innehåller alla fält, omformningar och utökade dimensioner som definieras i alla datauppsättningens konfigurationsfiler för datauppsättningsprofilen och eventuella ärvda profiler.
