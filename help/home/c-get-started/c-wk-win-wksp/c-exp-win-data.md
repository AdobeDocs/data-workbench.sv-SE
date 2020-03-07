---
description: Du kan exportera data i vissa fönster till en Excel-fil (.xls eller .xlsx) eller till en tabbseparerad värdefil (.tsv).
solution: Analytics
title: Exportera fönsterdata
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportera fönsterdata{#export-window-data}

Du kan exportera data i vissa fönster till en Excel-fil (.xls eller .xlsx) eller till en tabbseparerad värdefil (.tsv).

Data exporteras inte från diagram, sökvägsläsare, processkartor, spridningspunkterna och glober.

## Exportera fönsterdata till Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

Om du vill exportera enskilda fönsterdata till Microsoft Excel måste följande krav vara uppfyllda:

* Microsoft Excel måste vara installerat på samma dator som Data Workbench.
* Användarkontot som Data Workbench-processen körs under måste ha behörighet att komma åt Microsoft Excel.
* När du exporterar data som Excel-filer öppnar du en ny instans av Excel.
* Data Workbench stöder över 256 kolumner och 65 536 rader, men versioner av Microsoft Excel före 8.0 gör det inte.

Om dessa krav uppfylls startar Data Workbench automatiskt Microsoft Excel och exporterar data till en ny Excel-arbetsbok när du väljer **[!UICONTROL Export To Excel]** menyalternativet.

**Exportera fönsterdata till en .xls- eller .xlsx-fil**

Högerklicka på fönstrets övre kant och klicka **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel öppnar en ny arbetsbok som innehåller exporterade data. Om du inte har angett en anpassad titel (som beskrivs i följande avsnitt), får arbetsboken namnet med hjälp av [!DNL Export title] (dagstabellen i exemplet ovan).

## Använda anpassade titlar {#section-2a6559df812a470685e43923b7b9024e}

Om du anger en anpassad titel för ett fönster (med hjälp av [!DNL Custom title] fältet på [!DNL Export] menyn) namnges det kalkylblad som Data Workbench exporterar data till med den här anpassade titeln i stället för titeln i [!DNL Export title] fältet (dagstabell i exemplet ovan).

**Använda en anpassad titel på en visualisering**

1. Högerklicka på fönstrets övre kant och klicka i **[!UICONTROL Custom title]** fältet.
1. dig

![](assets/mnu_window_TitleBar_Export.png)

När du exporterar visualiseringen till Excel namnges kalkylbladet som innehåller data för det här fönstret med den titel som du angav i stället för titeln i [!DNL Export title] fältet.

## Exportera fönsterdata till en TSV-fil {#section-93c6b24f7338430aaf5a63b99b9489e8}

**Exportera ett fönster till en .tsv-fil**

Högerklicka på fönstrets övre kant och klicka **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. Dialogrutan [!DNL Save Window] visas.
1. Navigera till katalogen där du vill spara filen. Ändra namnet på filen om det behövs och klicka på **[!UICONTROL Save]**.

