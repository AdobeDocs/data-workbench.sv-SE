---
description: Information om hur du installerar en datatjänst på en data workbench-server.
solution: Analytics
title: Installera en datatjänst på en Data Workbench-server
topic: Data workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Installera en datatjänst på en Data Workbench-server{#installing-a-data-service-on-a-data-workbench-server}

Information om hur du installerar en datatjänst på en data workbench-server.

Om du använder IP Geo-Intelligence-datatjänsten eller IP Geo-location-datatjänsten måste du installera antingen [!DNL IP Geo-intelligence] - eller [!DNL IP Geo-location] -profilen och de relaterade sökfilerna på din data workbench-server. Du måste slutföra följande procedurer när du har installerat data workbench- [!DNL Geography] profilen. Se [Installera Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Om du inte har installerat data workbench följer du instruktionerna i användarhandboken *för* Data Workbench innan du fortsätter.

>[!NOTE]
>
>Om du vill installera datatjänstfilerna måste du ha tillgång till filerna på data workbench-servern.

Adobe distribuerar IP Geo-Intelligence och IP Geo-location-datatjänster som [!DNL .zip] filer. Varje [!DNL .zip] fil innehåller två mappar: Uppslag och profiler. Om du vill installera en datatjänst på data workbench-servern måste du utföra följande steg:

* Installera datatjänstprofilen. Se [Installera datatjänstprofilen](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Installera datatjänstens sökningar. Se [Installera söktjänstens filer](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

Du måste installera datatjänstprofilen och sökfilerna på den data workbench-serverdator som du bearbetar och kör datauppsättningsprofilen på. Om du kör ett data workbench-serverkluster måste du installera filerna på huvudservern. Mer information om datauppsättningsprofiler finns i konfigurationsguiden för *datauppsättningar*.
