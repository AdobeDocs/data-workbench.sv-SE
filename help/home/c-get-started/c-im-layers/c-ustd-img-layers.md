---
description: Konceptuell information om bildlager.
solution: Analytics
title: Om bildlager
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: f4b37f50b115a1e1d2c9d000897a8fa47b03b233
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---


# Om bildlager{#about-imagery-layers}

Konceptuell information om bildlager.

## Typer av bildlager {#section-891cbf61e8334690bd203a2bb9761b25}

Du kan visa följande typer av bildlager i Datan Workbench:

* **[!UICONTROL Terrain image layer]:** Den här typen av lager visar terrängbilder av jorden, över vilka geografiska data kan visas. Globens visualisering i är ett exempel på ett terrängbildslager. Se [Arbeta med terrängbildlager](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** Den här typen av lager visar en punkt på jorden för varje element i en dimension. Se [Arbeta med elementpunktslager](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Den här typen av lager visar vektordata (konturteckningar) på jorden. Se [Arbeta med vektorlager](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Kommentera och förtydliga visualiseringar med en presentationsövertäckning. Lägg till textanrop, pilar, bilder och färgkodning för att markera och förtydliga data och sedan dela dem med andra.

I Data Workbench kan du välja vilka av dessa lager du vill visa för en viss analysuppgift.

## Geografiska profillager {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Profilen innehåller en uppsättning [!DNL Geography] standardbildlager som lagras i mappen Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]:** Det här terrängbildslagret skapar en 3D-karta över världen, vilket är vad som visas när du lägger till globala visualiseringar på en arbetsyta. När det här lagret inte är markerat visas inte glöden, men de andra lagren visas fortfarande. Filen refererar [!DNL Blue Marble 2km.layer] till [!DNL Blue Marble 2km.tsi] filen.

* **[!UICONTROL Zip Points]:** Med det här elementpunktslagret kan du mappa platser i datauppsättningen med hjälp av en ZIP-kod i USA. Uppslagsfilen (tillhandahålls av Adobe) innehåller en lista över alla amerikanska ZIP-koder och varje ZIP-kods latitud och longitud. [!DNL Zip Points.txt] Filen refererar [!DNL Zip Points.layer] till [!DNL Zip Points.txt] filen och [!DNL Zipcode.dim] filen och innehåller de konfigurationsparametrar som behövs för att visa platserna i världen. Varje element i ZIP-koddimensionen ( [!DNL Zipcode.dim]) som du definierar i datauppsättningen mappas på jorden med den latitud och longitud som listas för den ZIP-koden i [!DNL Zip Points.txt] sökfilen.

   Mer information om hur du definierar dimensioner finns i *Konfigurationshandboken* för datauppsättningar.

* **[!UICONTROL Boundaries]:** Det här vektorskiktet utgör världens största politiska gränser, till exempel länder, liksom gränserna för jordens naturliga fysiska egenskaper, till exempel sjöar och öar. Filen refererar [!DNL Boundaries.layer] till en eller flera av [!DNL mwcoast.vec]-, [!DNL mwisland.vec]-, [!DNL mwlake.vec], [!DNL mwnation.vec]-, [!DNL mwriver.vec], [!DNL mwstate.vec]- [!DNL US states.vec]och [!DNL world boundaries.vec] -filerna.

* **[!UICONTROL IP Coordinates]:** I det här elementpunktslagret används dynamiska punkter för att mappa platser i datauppsättningen med hjälp av IP-adresser. Filen refererar till [!DNL IP Coordinates.layer] dimensionen Koordinater ( [!DNL Coordinates.dim]) och anger Visitors-måttet som det mätvärde som ska användas för att bestämma storleken på punkterna i världen för varje koordinat.

Din [!UICONTROL NL Geography] profil eller andra profiler i din installation kan innehålla ytterligare bildlager som Adobe har tillhandahållit eller som ditt företag har skapat.

## Skapa ett nytt lager {#section-b5313773316c4e0fa748f7376a8e7f0b}

Du kan skapa nya bildlager genom att kopiera lämplig typ av lagerfil som ingår i [!DNL Geography] profilen till en profilmapp\*profilnamn*\Kartor och sedan ändra namn på och redigera filen efter behov. Alla nya lager måste uppfylla följande krav:

* Filen måste [!DNL .layer] följa formatet för en av de lagertyper som stöds.
* Filen måste vid behov referera till rätt sök- och dimensionsfiler [!DNL .layer] .
* Den refererade sökfilen måste också lagras i Datans Workbench serverinstallationskatalog, och sökvägen måste anges korrekt i [!DNL .layer] filen.

Mer information om format och parametrar för varje typ av lagerfil och tillhörande filer finns i avsnittet om lämplig lagertyp i det här kapitlet.
