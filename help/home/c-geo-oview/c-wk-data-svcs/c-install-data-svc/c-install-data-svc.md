---
description: Information om hur du installerar en datatjänst på en data workbench-server.
title: Installera en datatjänst på en Data Workbench-server
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Installera en datatjänst på en Data Workbench-server{#installing-a-data-service-on-a-data-workbench-server}

{{eol}}

Information om hur du installerar en datatjänst på en data workbench-server.

Om du använder IP Geo-Intelligence-datatjänsten eller IP Geo-location-datatjänsten måste du installera antingen [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] profil och relaterade sökfiler på din data workbench-server. Du måste slutföra följande procedurer när du har installerat data workbench [!DNL Geography] profil. Se [Installerar Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Om du inte har installerat data workbench följer du instruktionerna i *Användarhandbok för Data Workbench* innan du fortsätter.

>[!NOTE]
>
>Om du vill installera datatjänstfilerna måste du ha tillgång till filerna på data workbench-servern.

Adobe distribuerar IP Geo-Intelligence och IP Geo-location-datatjänster som [!DNL .zip] filer. Varje [!DNL .zip] filen innehåller två mappar: Uppslag och profiler. Om du vill installera en datatjänst på data workbench-servern måste du utföra följande steg:

* Installera datatjänstprofilen. Se [Installera Data Service Profile](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Installera datatjänstens sökningar. Se [Installera söktjänstens filer](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

Du måste installera datatjänstprofilen och sökfilerna på den data workbench-serverdator som du bearbetar och kör datauppsättningsprofilen på. Om du kör ett data workbench-serverkluster måste du installera filerna på den överordnad servern. Mer information om datauppsättningsprofiler finns i *Konfigurationshandbok för datauppsättning*.
