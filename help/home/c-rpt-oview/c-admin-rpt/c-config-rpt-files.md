---
description: I rapportportalen kan du visa rapporter som skapats av Report Server som Excel-filer (.xls, .xlsx) eller .png-filer.
title: Konfigurera Report.cfg-filer
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---

# Konfigurera Report.cfg-filer{#configuring-report-cfg-files}

{{eol}}

I rapportportalen kan du visa rapporter som skapats av Report Server som Excel-filer (.xls, .xlsx) eller .png-filer.

Så här visar du en rapportuppsättning i [!DNL Report Portal]måste du ange följande parametrar i [!DNL Report.cfg] fil för den rapportuppsättningen:

* I **[!UICONTROL Output Root]** anger du dokumentroten för webbservern som används för portalen.
* I **[!UICONTROL Report Types]** anger du Excel, png och/eller miniatyrbild som rapporttyper som du vill generera.

När [!DNL Report Server] genererar rapporterna i de format som du har angett och placerar dem i dokumentroten på webbservern, vilket är den plats där du konfigurerar [!DNL Report Portal] för att få tillgång till rapporterna.

Mer information om [!DNL Report.cfg] parametrar, se [Parametrar för Report.cfg](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
