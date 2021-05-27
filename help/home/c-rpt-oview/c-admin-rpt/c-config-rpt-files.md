---
description: I rapportportalen kan du visa rapporter som skapats av Report Server som Excel-filer (.xls, .xlsx) eller .png-filer.
title: Konfigurera Report.cfg-filer
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---

# Konfigurerar Report.cfg-filer{#configuring-report-cfg-files}

I rapportportalen kan du visa rapporter som skapats av Report Server som Excel-filer (.xls, .xlsx) eller .png-filer.

Om du vill visa en rapportuppsättning i [!DNL Report Portal] måste du ange följande parametrar i [!DNL Report.cfg]-filen för den rapportuppsättningen:

* I parametern **[!UICONTROL Output Root]** anger du dokumentroten för webbservern som används för portalen.
* I parametern **[!UICONTROL Report Types]** anger du Excel, png och/eller miniatyrbild som de rapporttyper som du vill generera.

När [!DNL Report Server] genererar rapporter i de format som du har angett placeras dessa filer i webbserverns dokumentrot, som är den plats där du under installationen konfigurerar [!DNL Report Portal] för att få åtkomst till rapporterna.

Mer information om de specifika [!DNL Report.cfg]-parametrarna finns i [Report.cfg-parametrar](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
