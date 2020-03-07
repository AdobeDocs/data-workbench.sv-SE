---
description: Om du prenumererar på någon av datatjänsterna måste du regelbundet uppdatera de datatjänstfiler som tillhandahålls av Adobe.
solution: Analytics
title: Uppdaterar datatjänstfiler
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Uppdaterar datatjänstfiler{#updating-data-service-files}

Om du prenumererar på någon av datatjänsterna måste du regelbundet uppdatera de datatjänstfiler som tillhandahålls av Adobe.

För att kunna göra det måste du ha tillgång till filerna på data workbench-servern.

Om du vill läsa in [!DNL IP Geo-location] - eller [!DNL IP Geo-intelligence] datafiler måste du utföra följande procedurer.

## Ersätta datafilen {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Öppna arbetsytan genom att klicka på miniatyrbilden i Data Workbench på [!DNL Admin] > [!DNL Dataset and Profile] -fliken **[!UICONTROL Servers Manager]** . [!DNL Servers Manager] .

1. Högerklicka på ikonen för den data workbench-server som du vill läsa in filerna till i [!DNL Servers Manager] fönstret och klicka sedan på **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager]högerklickar du i **[!UICONTROL Temp]** kolumnen för **[!UICONTROL Lookups\IP Geo-location]** eller **[!UICONTROL Lookups\IP Geo-intelligence]** och klickar på **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Kopiera datafilen som tillhandahålls av Adobe till mappfönstret Lookups\IP Geo-location eller Lookups\IP Geo-Intelligence. [!DNL .bin]
1. Spara filen på data workbench-serverdatorn genom att högerklicka på [!DNL Temp] kolumnen för datafilen och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Om du kör ett kluster överför du filerna till huvuddata workbench-servern i klustret.

## Uppdaterar IPLookup-omvandling {#section-a8b99afe3eb04afabe88e15bd465f935}

1. Klicka på [!DNL Profile Manager], **[!UICONTROL Dataset]** och **[!UICONTROL Transformation]****[!UICONTROL Geography]**.

1. Högerklicka på bockmarkeringen bredvid [!DNL IP Lookup.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.

1. Högerklicka på den nya bockmarkeringen och klicka **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Ett fönster för omformningskonfiguration visas.

1. Klicka i fönstret **[!UICONTROL Transformation]** och sedan på **[!UICONTROL Transformations]**.

1. Leta reda på och klicka antingen **[!UICONTROL IPLookup Quova]** eller **[!UICONTROL IPLookup Digital Envoy]**.

1. För parametern File uppdaterar du namnet på filen så att det matchar namnet på den nya datafilen ( [!DNL .bin]) som tillhandahålls av Adobe.
1. Spara omvandlingskonfigurationsfilen genom att högerklicka **[!UICONTROL (modified)]** högst upp i konfigurationsfönstret och klicka på **[!UICONTROL Save]**.

1. Spara den ändrade konfigurationsfilen till varje profil som använder datatjänsten genom att högerklicka på bockmarkeringen bredvid [!DNL IP Lookup.cfg] i [!DNL User] kolumnen och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. Omformningen av data börjar efter synkronisering av datauppsättningsprofilen.

   Mer information om omformning av datauppsättningen finns i kapitlet om ombearbetning och omformning i konfigurationsguiden för *datauppsättningar*.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profiler som tillhandahålls av Adobe (inklusive [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence] ), eftersom ändringarna skrivs över när du installerar uppdateringar för dessa profiler.

Om du har installerat [!DNL IP Geo-intelligence] - och [!DNL IP Geo-location] datatjänsten för version 5.1 eller senare har du slutfört datatjänstens uppdatering. Om du har installerat [!DNL IP Geo-intelligence] - och [!DNL IP Geo-location] datatjänsten före version 5.1 måste du dock slutföra följande ytterligare procedurer.

## Ersätta uppslagsfilen {#section-ced1efa38a76419d812edd35423dbff7}

Du bör bara utföra följande steg om du har installerat [!DNL IP Geo-intelligence] - och [!DNL IP Geo-location] datatjänsten före version 5.1.

1. Klicka på [!DNL Server Files Manager]antingen **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** eller **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** och klicka sedan **[!UICONTROL Maps]** för att visa innehållet.

1. Högerklicka i **[!UICONTROL Temp]** kolumnen för **[!UICONTROL Maps]** och klicka **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Kopiera den nya [!DNL .txt] filen från Adobe till mappfönstret Kartor.
1. Spara filen på datorn med data workbench-servern genom att högerklicka på bockmarkeringen i [!DNL Temp] kolumnen för [!DNL .txt] filen och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Om du kör ett kluster överför du filerna till huvuddata workbench-servern i klustret.

## Uppdaterar lagerfilerna {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Du bör bara utföra följande steg om du har installerat [!DNL IP Geo-intelligence] - och [!DNL IP Geo-location] datatjänsten före version 5.1.

Utför dessa steg för varje lagerfil ( [!DNL .layer]) som refererar till [!DNL IP Geo-intelligence] - eller [!DNL IP Geo-location] uppslagsfilen ( [!DNL .txt]).

1. Öppna filen i en textredigerare som Anteckningar i mappen Profiler\*datatjänstens namn*\Maps i installationskatalogen för [!DNL .layer] data workbench-servern.

1. I [!DNL Data Paths] vektorn uppdaterar du namnet på [!DNL .txt] sökfilen så att det matchar namnet på den nya [!DNL .txt] filen från Adobe, vilket visas i följande exempel:

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. Spara den uppdaterade lagerfilen.
1. Upprepa steg 2 och 3 för varje [!DNL .layer] fil som refererar till [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] [!DNL .txt] filen.

