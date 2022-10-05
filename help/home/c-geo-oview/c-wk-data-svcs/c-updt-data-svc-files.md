---
description: Om du prenumererar på någon av datatjänsterna måste du regelbundet uppdatera de datatjänstfiler som tillhandahålls av Adobe.
title: Uppdaterar datatjänstfiler
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---

# Uppdaterar datatjänstfiler{#updating-data-service-files}

{{eol}}

Om du prenumererar på någon av datatjänsterna måste du regelbundet uppdatera de datatjänstfiler som tillhandahålls av Adobe.

För att kunna göra det måste du ha tillgång till filerna på data workbench-servern.

För inläsning [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence] datafiler måste du slutföra följande procedurer.

## Ersätta datafilen {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. I data workbench, på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna [!DNL Servers Manager] arbetsyta.

1. I [!DNL Servers Manager] högerklickar du på ikonen för den data workbench-server där du vill läsa in filerna och klickar på **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager], högerklicka i **[!UICONTROL Temp]** kolumn för **[!UICONTROL Lookups\IP Geo-location]** eller **[!UICONTROL Lookups\IP Geo-intelligence]** och klicka **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Kopiera [!DNL .bin] datafil som tillhandahålls av Adobe till mappfönstret Lookups\IP Geo-location eller Lookups\IP Geo-Intelligence.
1. Spara filen på data workbench-serverdatorn genom att högerklicka på [!DNL Temp] kolumn för datafilen och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   Om du kör ett kluster överför du filerna till den överordnad data workbench-servern i klustret.

## Uppdaterar IPLookup-omvandling {#section-a8b99afe3eb04afabe88e15bd465f935}

1. I [!DNL Profile Manager], klicka **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]** och **[!UICONTROL Geography]**.

1. Högerklicka på bockmarkeringen bredvid [!DNL IP Lookup.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.

1. Högerklicka på den nya bockmarkeringen och klicka **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Ett fönster för omformningskonfiguration visas.

1. I fönstret klickar du på **[!UICONTROL Transformation]** och sedan klicka **[!UICONTROL Transformations]**.

1. Leta reda på och klicka på **[!UICONTROL IPLookup Quova]** eller **[!UICONTROL IPLookup Digital Envoy]**.

1. För parametern File ska du uppdatera namnet på filen så att det matchar namnet på nya data ( [!DNL .bin]) från Adobe.
1. Spara omvandlingskonfigurationsfilen genom att högerklicka **[!UICONTROL (modified)]** högst upp i konfigurationsfönstret och klicka på **[!UICONTROL Save]**.

1. Spara den ändrade konfigurationsfilen till varje profil som använder datatjänsten genom att högerklicka på bockmarkeringen bredvid [!DNL IP Lookup.cfg] i [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. Omformningen av data börjar efter synkronisering av datauppsättningsprofilen.

   Mer information om omformning av datauppsättningen finns i kapitlet om ombearbetning och omformning i *Konfigurationshandbok för datauppsättning*.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe (inklusive [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence] profil) när ändringarna skrivs över när du installerar uppdateringar för dessa profiler.

Om du har installerat [!DNL IP Geo-intelligence] och [!DNL IP Geo-location] datatjänsten för version 5.1 eller senare har du slutfört datatjänstens uppdatering. Om du har installerat [!DNL IP Geo-intelligence] och [!DNL IP Geo-location] datatjänsten måste du utföra följande ytterligare procedurer innan version 5.1 börjar.

## Ersätta uppslagsfilen {#section-ced1efa38a76419d812edd35423dbff7}

Du bör bara utföra följande steg om du har installerat [!DNL IP Geo-intelligence] och [!DNL IP Geo-location] datatjänst före version 5.1.

1. I [!DNL Server Files Manager]klickar du på antingen **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** eller **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** och sedan klicka **[!UICONTROL Maps]** för att visa innehållet.

1. Högerklicka i dialogrutan **[!UICONTROL Temp]** kolumn för **[!UICONTROL Maps]** och klicka **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. Kopiera nya [!DNL .txt] som tillhandahålls av Adobe till mappfönstret för kartor.
1. Spara filen på data workbench-serverdatorn genom att högerklicka på bockmarkeringen i [!DNL Temp] kolumn för [!DNL .txt] fil och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Om du kör ett kluster överför du filerna till den överordnad data workbench-servern i klustret.

## Uppdaterar lagerfilerna {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>Du bör bara utföra följande steg om du har installerat [!DNL IP Geo-intelligence] och [!DNL IP Geo-location] datatjänst före version 5.1.

Slutför dessa steg för alla lager ( [!DNL .layer]) som refererar till [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] sökning ( [!DNL .txt]).

1. Öppna mappen Profiles\*data service name*\Maps i installationskatalogen för data workbench-servern i [!DNL .layer] i en textredigerare som Anteckningar.

1. I [!DNL Data Paths] vektor, uppdatera namnet på [!DNL .txt] sökfil som matchar namnet på den nya [!DNL .txt] som tillhandahålls av Adobe, vilket visas i följande filexempel:

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
1. Upprepa steg 2 och 3 för varje [!DNL .layer] som refererar till [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] [!DNL .txt] -fil.
