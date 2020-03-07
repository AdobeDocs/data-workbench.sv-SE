---
description: Om du vill identifiera system- och programfel så snart som möjligt och åtgärda dem innan de orsakar större problem eller avbrott bör du regelbundet övervaka dina händelseloggar.
solution: Insight
title: Övervaka händelser för fel
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Övervaka händelser för fel{#monitoring-events-for-errors}

Om du vill identifiera system- och programfel så snart som möjligt och åtgärda dem innan de orsakar större problem eller avbrott bör du regelbundet övervaka dina händelseloggar.

**Rekommenderad frekvens:** Var 5-10:e minut

Om du vill övervaka dina Adobe-serverprodukter kan du använda det automatiska hanteringsverktyget för att övervaka dina händelseloggar för fel med källan&quot;Adobe&quot; och sedan informera lämplig personal om problem som kan kräva åtgärder.

I Windows skickas programfelmeddelanden till programhändelseloggen i Windows, som du kommer åt med hjälp av Windows Event Viewer. I Unix skickas programfelmeddelanden till Unix-syslog med hjälp av LOG_DAEMON-funktionen.

**Så här öppnar du Windows Event Viewer**

* Klicka på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

