---
description: Datatjänstprofilerna (IP Geo-Intelligence och IP Geo-location) är interna profiler som ger ytterligare funktionalitet till Adobe.
title: Installera Data Service Profile
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 0%

---

# Installera datatjänstprofilen{#installing-the-data-service-profile}

Datatjänstprofilerna (IP Geo-Intelligence och IP Geo-location) är interna profiler som ger ytterligare funktionalitet till Adobe.

Precis som med alla andra interna profiler från Adobe bör dessa profiler inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

Datatjänstprofilerna innehåller följande datauppsättning som innehåller filer som ska installeras på en data workbench-server:

* **Profiler\*profilnamn *\Dataset\Log Processing\Traffic\IP.cfg:** Visar en lista över det c-ip-fält som ska skickas från loggbearbetning till omvandling.
* **Profiler\*profilnamn *\Dataset\Transformation\Geography\IPLookup.cfg:** Definierar en IPLookup-omvandling som skapar flera fält med geografiska data med hjälp av angiven IP Geo-Intelligence-fil eller IP Geo-location-sökningsfil.

Mer information om att inkludera filer i omformningsdatauppsättningar finns i *Konfigurationshandboken för datauppsättningar*.

Varje datatjänstprofil ger dig dessutom en elementpunktslagerfil med namnet [!DNL IP Coordinates.layer]. Med den här lagerfilen kan du dynamiskt mappa platser i datauppsättningen på jorden med hjälp av IP-adresser. Efter installationen lagras lagret i mappen Profiler\*datatjänstens namn*\Maps i installationskatalogen för data workbench-servern.

Filen [!DNL IP Coordinates.layer] refererar till dimensionen Koordinater, som definieras i filen [!DNL Coordinates.cfg] som finns i profilen [!DNL Geography] och som finns i mappen Dataset\Transformation\Geography folder. Varje element i dimensionen Koordinater som definieras i datamängden mappas på jorden med hjälp av latitud- och longitudinformationen som finns i det elementet. Mer information om elementpunktslager som använder dynamiska punkter finns i [Definiera elementpunktslager med hjälp av dynamiska punkter](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>Om du har installerat IP Geo-Intelligence och IP Geo-location-datatjänsten före version 5.1 refererar elementets punktskiktsfil till en sökfil i stället för att använda dynamiska punkter. Varje lagerfil refererar till IP-geokodssökningsfilen och IP-geokoddimensionen. Sökfilen för IP-geokoder innehåller en lista med IP-geokoder (geografiska platser baserade på IP-adressen) och latitud och longitud för varje. Varje element i en IP-geokoddimension som definieras i din datamängd mappas på jorden med de latitud- och longitudvärden som listas för den IP-geokoden i sökfilen för IP-geokoder.

Namnet på lagerfilen och de filer den refererar till skiljer sig åt för varje datatjänst:

* Filen [!DNL IP Geocodes D.layer] installeras med profilen IP Geo-Intelligence (Digital Envoy). Det här elementpunktslagret refererar till uppslagsfilen [!DNL IP Geocodes D yyyymmdd.txt] (som du måste uppdatera regelbundet) och dimensionen för IP-geokod D.

* Filen [!DNL IP Geocodes Q.layer] installeras med IP-profilen Geo-location (Quova). Det här elementpunktslagret refererar till uppslagsfilen [!DNL IP Geocodes Q yyyymmdd.txt] (som du måste uppdatera regelbundet) och IP-geokoddimensionen Q.

Mer information om elementpunktslager som använder sökfiler finns i [Definiera elementpunktslager som refererar till uppslagsfiler](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## Så här installerar du IP Geo-Intelligence eller IP Geo-location-profilen {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>I följande installationsanvisningar förutsätts att du har installerat data workbench och upprättat en anslutning mellan data workbench och den data workbench-server som du installerar data workbench [!DNL Geography] på. Om du inte har gjort det läser du *Datans Workbench användarhandbok*.

1. Öppna mappen Profiler från [!DNL .zip]-filen som du fick från Adobe.
1. Kopiera mappen IP Geo-Intelligence eller IP Geo-location till mappen Profiles i installationskatalogen för data workbench-servern. Vill du få en..?\Profiles\IP Geo-intelligence folder or a ..\Profiles\IP Geo-location on your data workbench server as shown in the following example. Namnen på de andra mapparna i mappen [!DNL Profiles] kan skilja sig från de som visas.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Följ de här stegen för att uppdatera [!DNL profile.cfg]-filen för varje profil som du vill använda profilen [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] med.

   1. Öppna **[!UICONTROL Profile Manager]**.
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Fönstret [!DNL profile.cfg] visas.

   1. Högerklicka på **[!UICONTROL Directories]** i [!DNL profile.cfg]fönstret och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Om du vill lägga till den nya katalogen i slutet av kataloglistan högerklickar du på numret eller namnet på den sista katalogen i listan och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Ange namnet på den nya katalogen: [!DNL IP Geo-intelligence] eller I [!DNL P Geo-location].

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager] högerklickar du på bockmarkeringen för [!DNL profile.cfg] i kolumnen [!DNL User] och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe (inklusive profilen [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence]) eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.
