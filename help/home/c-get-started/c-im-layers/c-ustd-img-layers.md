---
description: Konceptuell information om bildlager.
title: Om bildlager
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Om bildlager{#about-imagery-layers}

{{eol}}

Konceptuell information om bildlager.

## Typer av bildlager {#section-891cbf61e8334690bd203a2bb9761b25}

Du kan visa följande typer av bildlager i Datan Workbench:

* **[!UICONTROL Terrain image layer]:** Den här typen av lager visar terrängbilder av jorden, över vilka geografiska data kan visas. Globens visualisering i är ett exempel på ett terrängbildslager. Se [Arbeta med terrängbildlager](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** Den här typen av lager visar en punkt på jorden för varje element i en dimension. Se [Arbeta med elementpunktslager](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Den här typen av lager visar vektordata (konturteckningar) på jorden. Se [Arbeta med vektorlager](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Kommentera och förtydliga visualiseringar med en presentationsövertäckning. Lägg till textanrop, pilar, bilder och färgkodning för att markera och förtydliga data och sedan dela dem med andra.

I Data Workbench kan du välja vilka av dessa lager du vill visa för en viss analysuppgift.

## Geografiska profillager {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

The [!DNL Geography] Med profilen får du en uppsättning standardbildlager som lagras i mappen Profiler\Geography\Maps i Datans Workbench installationskatalog:

* **[!UICONTROL Blue Marble 2km]:** Det här terrängbildslagret skapar en 3D-karta över världen, vilket är vad som visas när du lägger till globala visualiseringar på en arbetsyta. När det här lagret inte är markerat visas inte glöden, men de andra lagren visas fortfarande. The [!DNL Blue Marble 2km.layer] filen refererar till [!DNL Blue Marble 2km.tsi] -fil.

* **[!UICONTROL Zip Points]:** Med det här elementpunktslagret kan du mappa platser i datauppsättningen med hjälp av en ZIP-kod i USA. The [!DNL Zip Points.txt] Uppslagsfilen (tillhandahålls av Adobe) innehåller en lista över alla amerikanska ZIP-koder och varje ZIP-kods latitud och longitud. The [!DNL Zip Points.layer] filen refererar till [!DNL Zip Points.txt] -filen och [!DNL Zipcode.dim] filen och innehåller de konfigurationsparametrar som behövs för att visa platserna i världen. Varje element i postnummer-dimensionen ( [!DNL Zipcode.dim]) som du definierar i datauppsättningen mappas på jorden med latitud och longitud som listas för den ZIP-koden i [!DNL Zip Points.txt] sökfil.

   Mer information om hur du definierar dimensioner finns i *Konfigurationshandbok för datauppsättning*.

* **[!UICONTROL Boundaries]:** Det här vektorskiktet utgör världens största politiska gränser, till exempel länder, liksom gränserna för jordens naturliga fysiska egenskaper, till exempel sjöar och öar. The [!DNL Boundaries.layer] filen refererar till en eller flera av [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]och [!DNL world boundaries.vec] filer.

* **[!UICONTROL IP Coordinates]:** I det här elementpunktslagret används dynamiska punkter för att mappa platser i datauppsättningen med hjälp av IP-adresser. The [!DNL IP Coordinates.layer] filen refererar till dimensionen Koordinater ( [!DNL Coordinates.dim]) och anger Visitors-måttet som det mätvärde som ska användas för att bestämma storleken på punkterna i världen för varje koordinat.

Dina [!UICONTROL NL Geography] profiler eller andra profiler i installationen kan innehålla ytterligare bildlager som Adobe har skapat eller som företaget har skapat.

## Skapa ett nytt lager {#section-b5313773316c4e0fa748f7376a8e7f0b}

Du kan skapa nya bildlager genom att kopiera lämplig typ av lagerfil som finns i [!DNL Geography] till en profil\*profilnamn*\Mappar och byter sedan namn på och redigerar filen efter behov. Alla nya lager måste uppfylla följande krav:

* The [!DNL .layer] filen måste följa formatet för en av de lagertyper som stöds.
* The [!DNL .layer] filen måste referera till rätt sök- och dimensionsfiler, om det behövs.
* Den refererade sökfilen måste också lagras i Datans Workbench serverinstallationskatalog, och sökvägen måste anges korrekt i [!DNL .layer] -fil.

Mer information om format och parametrar för varje typ av lagerfil och tillhörande filer finns i avsnittet om lämplig lagertyp i det här kapitlet.
