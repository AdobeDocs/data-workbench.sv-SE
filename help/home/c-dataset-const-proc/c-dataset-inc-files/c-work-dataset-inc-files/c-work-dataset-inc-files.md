---
description: Datauppsättningen innehåller filer som är ett flexibelt sätt att konfigurera datauppsättningen.
solution: Analytics
title: Arbeta med datauppsättningen Inkludera filer
topic: Data workbench
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arbeta med datauppsättningen Inkludera filer{#working-with-dataset-include-files}

Datauppsättningen innehåller filer som är ett flexibelt sätt att konfigurera datauppsättningen.

I varje fil kan du definiera så få eller så många fält, omformningar eller dimensioner du vill, och du kan ordna inkluderingsfilerna baserat på den ärvda profil som de tillhör. När du konfigurerar datauppsättningen kan du redigera datauppsättningen och inkludera filer som ingår i de interna profilerna för ditt Adobe-program eller skapa nya datauppsättningsinkluderingsfiler för eventuella ärvda profiler som du skapar.

När du redigerar parametrarna för en datauppsättning inkluderar en fil för en intern profil och sparar den uppdaterade filen i datauppsättningsprofilen eller en ärvd profil som du skapar, åsidosätter du i själva verket filens ursprungliga inställningar. Adobe rekommenderar att du redigerar en datauppsättning som innehåller en fil för en intern profil när du behöver göra mindre ändringar i datauppsättningens innehåll, till exempel ändra en villkorsparameter eller en parameters standardinställning. Se [Redigera befintlig datauppsättning Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). Men om du vill ange ett nytt fält som ska skickas från loggbearbetning till omvandling, uppdatera eller skapa nya fält med omformningar, eller definiera utökade dimensioner, är det bäst att skapa en ny inkluderingsfil för datauppsättningar. Se [Skapa ny datauppsättning med filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). Du kan redigera filen som du skapar när eller hur du vill.