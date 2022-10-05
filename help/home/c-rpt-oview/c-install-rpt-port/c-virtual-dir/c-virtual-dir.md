---
description: Om du vill konfigurera rapportportalen måste du mappa dess programfiler till virtuella kataloger.
title: Mappa rapportportalsidor till virtuella kataloger
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# Mappa rapportportalsidor till virtuella kataloger{#map-the-report-portal-pages-to-virtual-directories}

{{eol}}

Om du vill konfigurera rapportportalen måste du mappa dess programfiler till virtuella kataloger.

En virtuell katalog definierar den adress som webbläsarklienter använder för att hitta en fysisk resurs på IIS-programservern. För åtkomst [!DNL Report Portal], pekar klienterna på sina webbläsare mot den virtuella katalog som du tilldelar portalen.

Namnet på den virtuella katalog som du tilldelar till [!DNL Report Portal] måste matcha namnet som du använde för mappen VSVirtualPortalName i steg 3 i föregående avsnitt. Om du till exempel vill använda&quot;Portal&quot; som namn på [!DNL Report Portal]måste du mappa portalens filer till en virtuell katalog med namnet&quot;Portal&quot;. I följande exempel visas den URI som klienter använder för att få åtkomst till en [!DNL Report Portal] som tilldelats till den virtuella katalogen [!DNL VisualReportPortal] på en server med namnet myWebServer:

[!DNL https://myWebServer/VisualReportPortal]

Följande procedurer beskriver hur du mappar [!DNL Report Portal] till en virtuell katalog i IIS 5.0, 6.0 och 7.0 eller senare.

Följ de här procedurerna för den version av IIS som du använder:

* [Mappa rapportportalen till en virtuell katalog (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Mappningsrapportportal till en virtuell katalog (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Redigera sessionskonfigurationsfilen](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
