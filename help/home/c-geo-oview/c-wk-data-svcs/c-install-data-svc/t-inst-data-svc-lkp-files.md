---
description: Steg för att installera IP Geo-Intelligence- eller IP Geo-location-sökfiler.
title: Installerar Data Service Lookup-filer
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Installerar Data Service Lookup-filer{#installing-the-data-service-lookup-files}

{{eol}}

Steg för att installera IP Geo-Intelligence- eller IP Geo-location-sökfiler.

Uppslagsfilen (Lookups\*profilnamn*\*datafilnamn*) som tillhandahålls med datatjänstprofilen är en binär fil ( [!DNL .bin]) som innehåller geografiskt relaterade data baserade på IP-adressen. Du måste ersätta den här filen regelbundet för att se till att du har de senaste geografiska data. Se [Uppdaterar datatjänstfiler](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Så här installerar du IP Geo-Intelligence- eller IP Geo-location-sökfiler**

>[!NOTE]
>
>Alla dina [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence] datafiler måste få plats i det tillgängliga fysiska minnet på din data workbench-server.

1. Öppna mappen Uppslag från [!DNL .zip] som du har fått från Adobe.
1. Kopiera mappen IP Geo-Intelligence eller IP Geo-location till mappen Lookups i installationskatalogen för data workbench-servern (du vill avsluta med en ...\Söker\IP GeoIntelligence eller en ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. Namnen på de andra mapparna i mappen Uppslag kan skilja sig från de som visas.

   ![Steginformation](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Adobe skickar regelbundet filer som innehåller uppdaterade [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] sökfiler. När du tar emot dessa filer måste du läsa in dem på din data workbench-server enligt instruktionerna från Adobe. Instruktioner finns i följande avsnitt.
