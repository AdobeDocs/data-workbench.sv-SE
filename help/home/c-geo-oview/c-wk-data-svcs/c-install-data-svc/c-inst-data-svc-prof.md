---
description: Datatjänstprofilerna (IP Geo-Intelligence och IP Geo-location) är interna profiler som ger ytterligare funktionalitet till Adobe.
title: Installera Data Service Profile
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 0%

---

# Installera Data Service Profile{#installing-the-data-service-profile}

{{eol}}

Datatjänstprofilerna (IP Geo-Intelligence och IP Geo-location) är interna profiler som ger ytterligare funktionalitet till Adobe.

Precis som med alla andra interna profiler från Adobe bör dessa profiler inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

Datatjänstprofilerna innehåller följande datauppsättning som innehåller filer som ska installeras på en data workbench-server:

* **Profiler\*profilnamn *\Dataset\Loggbearbetning\Trafik\IP.cfg:** Visar det c-ip-fält som ska skickas från loggbearbetning till omformning.
* **Profiler\*profilnamn *\Dataset\Transformation\Geography\IPLookup.cfg:** Definierar en IPLookup-omvandling som skapar flera fält med geografiska data med hjälp av den angivna IP-geo-Intelligence- eller IP-geo-location-sökfilen.

Mer information om att inkludera filer i omformningsdatauppsättningen finns i *Konfigurationshandbok för datauppsättning*.

Dessutom får du med varje datatjänstprofil en elementpunktskiktfil med namnet [!DNL IP Coordinates.layer]. Med den här lagerfilen kan du dynamiskt mappa platser i datauppsättningen på jorden med hjälp av IP-adresser. Efter installationen lagras lagret i mappen Profiler\*datatjänstens namn*\Maps i installationskatalogen för data workbench-servern.

The [!DNL IP Coordinates.layer] filen refererar till dimensionen Koordinater, som definieras i [!DNL Coordinates.cfg] filen finns i [!DNL Geography] och finns i mappen Dataset\Transformation\Geography. Varje element i dimensionen Koordinater som definieras i datamängden mappas på jorden med hjälp av latitud- och longitudinformationen som finns i det elementet. Mer information om elementpunktslager som använder dynamiska punkter finns i [Definiera elementpunktslager med hjälp av dynamiska punkter](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Om du har installerat IP Geo-Intelligence och IP Geo-location-datatjänsten före version 5.1 refererar elementets punktskiktsfil till en sökfil i stället för att använda dynamiska punkter. Varje lagerfil refererar till IP-geokodssökningsfilen och IP-geokoddimensionen. Sökfilen för IP-geokoder innehåller en lista med IP-geokoder (geografiska platser baserade på IP-adressen) och latitud och longitud för varje. Varje element i en IP-geokoddimension som definieras i din datamängd mappas på jorden med de latitud- och longitudvärden som listas för den IP-geokoden i sökfilen för IP-geokoder.

Namnet på lagerfilen och de filer den refererar till skiljer sig åt för varje datatjänst:

* The [!DNL IP Geocodes D.layer] filen installeras med profilen IP Geo-Intelligence (Digital Envoy). Det här elementpunktslagret refererar till [!DNL IP Geocodes D yyyymmdd.txt] sökfil (som du behöver uppdatera regelbundet) och IP-geokod D-dimensionen.

* The [!DNL IP Geocodes Q.layer] filen installeras med IP-profilen Geo-location (Quova). Det här elementpunktslagret refererar till [!DNL IP Geocodes Q yyyymmdd.txt] sökfil (som du måste uppdatera regelbundet) och IP-geokoddimension Q.

Mer information om elementpunktslager som använder sökfiler finns i [Definiera elementpunktslager som refererar till sökfiler](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## Så här installerar du IP Geo-Intelligence eller IP Geo-location-profilen {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>I följande installationsanvisningar förutsätts att du har installerat data workbench och upprättat en anslutning mellan data workbench och den data workbench-server som du installerar data workbench på [!DNL Geography]. Om du inte har gjort det kan du läsa *Användarhandbok för Data Workbench*.

1. Öppna mappen Profiler från [!DNL .zip] som du har fått från Adobe.
1. Kopiera mappen IP Geo-Intelligence eller IP Geo-location till mappen Profiles i installationskatalogen för data workbench-servern. Vill du få en..?\Profiler\IP GeoIntelligence-mapp eller en ...\Profiles\IP Geo-location på din data workbench-server som i följande exempel. Namnen på de andra mapparna i [!DNL Profiles] -mappen kan skilja sig från de som visas.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Använd följande steg för att uppdatera [!DNL profile.cfg] för varje profil som du vill använda [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] profil.

   1. Öppna **[!UICONTROL Profile Manager]**.
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL profile.cfg] visas.

   1. I [!DNL profile.cfg]fönster, högerklicka **[!UICONTROL Directories]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Om du vill lägga till den nya katalogen i slutet av kataloglistan högerklickar du på numret eller namnet på den sista katalogen i listan och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Ange namnet på den nya katalogen: [!DNL IP Geo-intelligence] eller I [!DNL P Geo-location].

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager], högerklicka på bockmarkeringen för [!DNL profile.cfg] i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe (inklusive [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence] profil) när ändringarna skrivs över när du installerar uppdateringar för dessa profiler.
