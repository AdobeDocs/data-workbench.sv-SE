---
description: Om du vill konfigurera rapportportalen måste du mappa dess programfiler till virtuella kataloger.
solution: Analytics
title: Mappa rapportportalsidor till virtuella kataloger
topic: Data workbench
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappa rapportportalsidor till virtuella kataloger{#map-the-report-portal-pages-to-virtual-directories}

Om du vill konfigurera rapportportalen måste du mappa dess programfiler till virtuella kataloger.

En virtuell katalog definierar den adress som webbläsarklienter använder för att hitta en fysisk resurs på IIS-programservern. För att få åtkomst till [!DNL Report Portal]klienten pekar klientens webbläsare mot den virtuella katalog som du har tilldelat portalen.

Namnet på den virtuella katalog som du tilldelar [!DNL Report Portal] måste matcha namnet som du använde för mappen VSVirtualPortalName i steg 3 i föregående avsnitt. Om du till exempel vill använda &quot;Portal&quot; som namn på portalen [!DNL Report Portal]måste du mappa portalfilerna till en virtuell katalog med namnet &quot;Portal&quot;. I följande exempel visas den URI som klienter använder för att komma åt en [!DNL Report Portal] tilldelad virtuell katalog [!DNL VisualReportPortal] på en server som heter myWebServer:

[!DNL http://myWebServer/VisualReportPortal]

Följande procedurer beskriver hur du mappar [!DNL Report Portal] till en virtuell katalog i IIS 5.0, 6.0 och 7.0 eller senare.

Följ de här procedurerna för den version av IIS som du använder:

* [Mappa rapportportalen till en virtuell katalog (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Mappningsrapportportal till en virtuell katalog (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Redigera sessionskonfigurationsfilen](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)

