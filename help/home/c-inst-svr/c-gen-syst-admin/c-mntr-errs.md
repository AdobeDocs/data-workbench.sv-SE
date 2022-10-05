---
description: Om du vill identifiera system- och programfel så snart som möjligt och åtgärda dem innan de orsakar större problem eller avbrott bör du regelbundet övervaka dina händelseloggar.
title: Övervaka händelser för fel
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Övervaka händelser för fel{#monitoring-events-for-errors}

{{eol}}

Om du vill identifiera system- och programfel så snart som möjligt och åtgärda dem innan de orsakar större problem eller avbrott bör du regelbundet övervaka dina händelseloggar.

**Rekommenderad frekvens:** Var 5-10:e minut

Om du vill övervaka dina serverprogramvaruprodukter från Adobe kan du ställa in det automatiska hanteringsverktyget så att du kan övervaka dina händelseloggar för fel med källan&quot;Adobe&quot; och sedan informera lämplig personal om problem som kan kräva åtgärder.

I Windows skickas programfelmeddelanden till programhändelseloggen i Windows, som du kommer åt med hjälp av Windows Event Viewer. I Unix skickas programfelmeddelanden till Unix-syslog med hjälp av LOG_DAEMON-funktionen.

**Så här öppnar du Windows Event Viewer**

* Klicka på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.
