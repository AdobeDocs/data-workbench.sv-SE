---
description: Du kan exportera data i vissa fönster till en Excel-fil (.xls eller .xlsx) eller till en tabbseparerad värdefil (.tsv).
title: Exportera fönsterdata
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# Exportera fönsterdata{#export-window-data}

{{eol}}

Du kan exportera data i vissa fönster till en Excel-fil (.xls eller .xlsx) eller till en tabbseparerad värdefil (.tsv).

Data exporteras inte från diagram, sökvägsläsare, processkartor, spridningspunkterna och glober.

## Exportera fönsterdata till Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Om du vill exportera enskilda fönsterdata till Microsoft Excel måste följande krav vara uppfyllda:

* Microsoft Excel måste vara installerat på samma dator som Datan Workbench.
* Användarkontot som Datan Workbench körs under måste ha behörighet att komma åt Microsoft Excel.
* När du exporterar data som Excel-filer öppnar du en ny instans av Excel.
* Data Workbench stöder över 256 kolumner och 65 536 rader, men versioner av Microsoft Excel före 8.0 gör det inte.

Om dessa krav uppfylls startar Datan Workbench automatiskt Microsoft Excel och exporterar data till en ny Excel-arbetsbok när du väljer **[!UICONTROL Export To Excel]** menyalternativ.

**Exportera fönsterdata till en .xls- eller .xlsx-fil**

Högerklicka på fönstrets övre kant och klicka på **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel öppnar en ny arbetsbok som innehåller exporterade data. Om du inte har angett en egen titel (som beskrivs i följande avsnitt), får arbetsboken ett namn med hjälp av [!DNL Export title] (Day Table i exemplet ovan).

## Använda anpassade titlar {#section-2a6559df812a470685e43923b7b9024e}

Om du anger en anpassad rubrik för ett fönster (med [!DNL Custom title] på [!DNL Export] -menyn) det kalkylblad som Datan Workbench exporterar data till får ett namn med hjälp av den här anpassade titeln i stället för rubriken i [!DNL Export title] (Dag-tabell i exemplet ovan).

**Använda en anpassad titel på en visualisering**

1. Högerklicka på fönstrets övre kant och klicka på **[!UICONTROL Custom title]** fält.
1. dig

![](assets/mnu_window_TitleBar_Export.png)

När du exporterar visualiseringen till Excel namnges kalkylbladet som innehåller data för det här fönstret med den titel som du angav i stället för titeln i [!DNL Export title] fält.

## Exportera fönsterdata till en TSV-fil {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Exportera ett fönster till en .tsv-fil**

Högerklicka på fönstrets övre kant och klicka på **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. The [!DNL Save Window] visas.
1. Navigera till katalogen där du vill spara filen. Ändra filens namn om det behövs och klicka på **[!UICONTROL Save]**.
