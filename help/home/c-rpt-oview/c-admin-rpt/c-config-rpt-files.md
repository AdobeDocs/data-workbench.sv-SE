---
description: I rapportportalen kan du visa rapporter som skapats av Report Server som Excel-filer (.xls, .xlsx) eller .png-filer.
solution: Analytics
title: Konfigurera Report.cfg-filer
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera Report.cfg-filer{#configuring-report-cfg-files}

I rapportportalen kan du visa rapporter som skapats av Report Server som Excel-filer (.xls, .xlsx) eller .png-filer.

Om du vill visa en rapportuppsättning i [!DNL Report Portal]måste du ange följande parametrar i [!DNL Report.cfg] filen för den rapportuppsättningen:

* Ange dokumentroten för den webbserver som används för portalen i **[!UICONTROL Output Root]** parametern.
* I **[!UICONTROL Report Types]** parametern anger du Excel, png och/eller miniatyrbild som de rapporttyper som du vill generera.

När [!DNL Report Server] genererar rapporter i de format som du har angett placeras dessa filer i dokumentroten på webbservern, vilket är den plats där du under installationen konfigurerar [!DNL Report Portal] att få åtkomst till rapporterna.

Mer information om de specifika [!DNL Report.cfg] parametrarna finns i [Report.cfg Parameters](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
