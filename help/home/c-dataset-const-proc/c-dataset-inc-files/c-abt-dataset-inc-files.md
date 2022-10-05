---
description: Många av de interna profiler som du har fått med programmet Adobe har egna konfigurationsfiler för datauppsättningar.
title: Om Inkludera datauppsättningar
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---

# Om Inkludera datauppsättningar{#about-dataset-include-files}

{{eol}}

Många av de interna profiler som du har fått med programmet Adobe har egna konfigurationsfiler för datauppsättningar.

Eftersom de interna profilerna är underprofiler till datauppsättningsprofilen innehåller deras datauppsättningskonfigurationsfiler regler som tillhandahåller ytterligare parametrar för loggbehandlings- eller transformeringsfaserna i datauppsättningskonstruktionen. Datauppsättningskonfigurationsfilerna för interna profiler och för eventuella ärvda profiler som du skapar kallas datauppsättningsfiler.

En datauppsättningsfil innehåller en delmängd av parametrarna som finns i konfigurationsfilerna för huvuddatamängden ( [!DNL Log Processing.cfg] eller [!DNL Transformation.cfg]) för datauppsättningsprofilen. Datauppsättningen innehåller filer som innehåller parametrar som är kopplade till loggbearbetningen som anropas [!DNL Log Processing Dataset Include] filer (se [Loggbehandlings-datauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), medan datauppsättningen innehåller filer som är kopplade till omvandlingen anropas [!DNL Transformation Dataset Include] Filer. Se [Omvandlingsdatauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Du kan skapa flera datauppsättningar med filer som ska användas i datauppsättningsprocessen. Den fullständiga datauppsättningen innehåller alla fält, omformningar och utökade dimensioner som definieras i alla datauppsättningens konfigurationsfiler för datauppsättningsprofilen och eventuella ärvda profiler.
