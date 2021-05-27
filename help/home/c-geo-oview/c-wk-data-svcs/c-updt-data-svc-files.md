---
description: Om du prenumererar på någon av datatjänsterna måste du regelbundet uppdatera de datatjänstfiler som tillhandahålls av Adobe.
title: Uppdaterar datatjänstfiler
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---

# Uppdaterar datatjänstfiler{#updating-data-service-files}

Om du prenumererar på någon av datatjänsterna måste du regelbundet uppdatera de datatjänstfiler som tillhandahålls av Adobe.

För att kunna göra det måste du ha tillgång till filerna på data workbench-servern.

Om du vill läsa in [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence] datafiler måste du slutföra följande procedurer.

## Ersätta datafilen {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. I data workbench klickar du på miniatyrbilden för [!DNL Admin] > [!DNL Dataset and Profile] på fliken **[!UICONTROL Servers Manager]** för att öppna arbetsytan för [!DNL Servers Manager].

1. I fönstret [!DNL Servers Manager] högerklickar du på ikonen för den data workbench-server som du vill läsa in filerna på och klickar på **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager] högerklickar du i kolumnen **[!UICONTROL Temp]** för **[!UICONTROL Lookups\IP Geo-location]** eller **[!UICONTROL Lookups\IP Geo-intelligence]** och klickar på **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]***.

1. Kopiera [!DNL .bin]-datafilen från Adobe till mappfönstret Lookups\IP Geo-location eller Lookups\IP Geo-Intelligence.
1. Spara filen på data workbench-serverdatorn genom att högerklicka på kolumnen [!DNL Temp] för datafilen och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Om du kör ett kluster överför du filerna till den överordnad data workbench-servern i klustret.

## Uppdaterar IPLookup-transformeringen {#section-a8b99afe3eb04afabe88e15bd465f935}

1. Klicka på **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** och **[!UICONTROL Geography]** i [!DNL Profile Manager].

1. Högerklicka på bockmarkeringen bredvid [!DNL IP Lookup.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].

1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Ett fönster för omformningskonfiguration visas.

1. Klicka på **[!UICONTROL Transformation]** i fönstret och klicka sedan på **[!UICONTROL Transformations]**.

1. Leta reda på och klicka på antingen **[!UICONTROL IPLookup Quova]** eller **[!UICONTROL IPLookup Digital Envoy]**.

1. För parametern File uppdaterar du namnet på filen så att det matchar namnet på den nya datafilen ( [!DNL .bin]) som tillhandahålls av Adobe.
1. Spara omvandlingskonfigurationsfilen genom att högerklicka på **[!UICONTROL (modified)]** högst upp i konfigurationsfönstret och klicka på **[!UICONTROL Save]**.

1. Spara den ändrade konfigurationsfilen i varje profil som använder datatjänsten genom att högerklicka på bockmarkeringen bredvid [!DNL IP Lookup.cfg] i kolumnen [!DNL User] och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. Omformningen av data börjar efter synkronisering av datauppsättningsprofilen.

   Mer information om omformning av datauppsättningen finns i kapitlet om ombearbetning och omformning i *konfigurationsguiden för datauppsättningar*.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe (inklusive profilen [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence]) eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

Om du har installerat datatjänsten [!DNL IP Geo-intelligence] och [!DNL IP Geo-location] för version 5.1 eller senare har du slutfört datatjänstens uppdatering. Om du har installerat datatjänsten [!DNL IP Geo-intelligence] och [!DNL IP Geo-location] före version 5.1 måste du dock slutföra följande ytterligare procedurer.

## Ersätta uppslagsfilen {#section-ced1efa38a76419d812edd35423dbff7}

Du bör bara utföra följande steg om du har installerat datatjänsten [!DNL IP Geo-intelligence] och [!DNL IP Geo-location] före version 5.1.

1. I [!DNL Server Files Manager] klickar du antingen på **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** eller **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** och sedan på **[!UICONTROL Maps]** för att visa innehållet.

1. Högerklicka i kolumnen **[!UICONTROL Temp]** för **[!UICONTROL Maps]** och klicka på **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Kopiera den nya [!DNL .txt]-filen från Adobe till mappfönstret Kartor.
1. Spara filen på data workbench-serverdatorn genom att högerklicka på bockmarkeringen i kolumnen [!DNL Temp] för [!DNL .txt]-filen och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Om du kör ett kluster överför du filerna till den överordnad data workbench-servern i klustret.

## Uppdaterar lagerfilerna {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Du bör bara utföra följande steg om du har installerat datatjänsten [!DNL IP Geo-intelligence] och [!DNL IP Geo-location] före version 5.1.

Utför dessa steg för varje lagerfil ( [!DNL .layer]) som refererar till [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location]-sökfilen ( [!DNL .txt]).

1. I mappen Profiler\*datatjänstens namn*\Maps i installationskatalogen för data workbench-servern öppnar du filen [!DNL .layer] i en textredigerare som Anteckningar.

1. I [!DNL Data Paths]-vektorn uppdaterar du namnet på [!DNL .txt]-sökfilen så att det matchar namnet på den nya [!DNL .txt]-filen som tillhandahålls av Adobe, vilket visas i följande filexempel:

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
1. Upprepa steg 2 och 3 för varje [!DNL .layer]-fil som refererar till [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] [!DNL .txt]-filen.
