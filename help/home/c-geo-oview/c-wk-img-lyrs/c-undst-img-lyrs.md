---
description: Konceptuell information om lager för geografiska profiler, typer av bildlager och hur du skapar nya lager.
title: Bildlager
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 0%

---

# Bildlager{#understanding-imagery-layers}

{{eol}}

Konceptuell information om lager för geografiska profiler, typer av bildlager och hur du skapar nya lager.

## Typer av bildlager {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data workbench [!DNL Geography] I kan du visa följande typer av bildlager i data workbench:

* **Terrängbildlager:** Den här typen av lager visar terrängbilder av jorden, över vilka geografiska data kan visas. Globens visualisering i data workbench är ett exempel på ett terrängbildslager. Se [Arbeta med terrängbildlager](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Elementpunktslager:** Den här typen av lager visar en punkt på jorden för varje element i en dimension. Se [Arbeta med elementpunktslager](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Vektorlager:** Den här typen av lager visar vektordata (konturteckningar) på jorden. Se [Arbeta med vektorlager](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

I data workbench kan du välja vilka av dessa lager du vill visa för en viss analysuppgift.

## Geografiska profillager {#section-4d9fb9b357764493a4d97d2b4068bb67}

The [!DNL Geography] profil innehåller en uppsättning standardbildlager som lagras i mappen Profiler\Geography\Maps i installationskatalogen för data workbench-servern:

* **Blå marmor 2 km:** Det här terrängbildslagret skapar en 3D-karta över världen, vilket är vad som visas när du lägger till globala visualiseringar på en arbetsyta. När det här lagret inte är markerat visas inte glöden, men de andra lagren visas fortfarande. The [!DNL Blue Marble 2km.layer] filen refererar till [!DNL Blue Marble 2km.tsi] -fil.

   Mer information om hur du arbetar med globala visualiseringar finns i *Användarhandbok för Data Workbench*.

* **Postnummer:** Med det här elementpunktslagret kan du mappa platser i datauppsättningen med hjälp av en ZIP-kod i USA. The [!DNL Zip Points.txt] Uppslagsfilen (tillhandahålls av Adobe) innehåller en lista över alla amerikanska ZIP-koder och varje ZIP-kods latitud och longitud. The [!DNL Zip Points.layer] filen refererar till [!DNL Zip Points.txt] -filen och [!DNL Zipcode.dim] filen och innehåller de konfigurationsparametrar som behövs för att visa platserna i världen. Varje element i postnummer-dimensionen ( [!DNL Zipcode.dim]) som du definierar i datauppsättningen mappas på jorden med latitud och longitud som listas för den ZIP-koden i [!DNL Zip Points.txt] sökfil.

   Mer information om hur du definierar dimensioner finns i *Konfigurationshandbok för datauppsättningar.*

* **Gränser:** Det här vektorskiktet utgör världens största politiska gränser, till exempel länder, liksom gränserna för jordens naturliga fysiska egenskaper, till exempel sjöar och öar. The [!DNL Boundaries.layer] filen refererar till en eller flera av [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]och [!DNL world boundaries.vec] filer.

* **IP-koordinater:** I det här elementpunktslagret används dynamiska punkter för att mappa platser i datauppsättningen med hjälp av IP-adresser. The [!DNL IP Coordinates.layer] filen refererar till dimensionen Koordinater ( [!DNL Coordinates.dim]) och anger Visitors-måttet som det mätvärde som ska användas för att bestämma storleken på punkterna i världen för varje koordinat.

Dina [!DNL Geography] profiler eller andra profiler i installationen kan innehålla ytterligare bildlager som Adobe har skapat eller som företaget har skapat.

## Skapa nya lager {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Du kan skapa nya bildlager genom att kopiera lämplig typ av lagerfil som finns i [!DNL Geography] till en profil\*profilnamn*\Mappar och byter sedan namn på och redigerar filen efter behov. Alla nya lager måste uppfylla följande krav:

* The [!DNL .layer] filen måste följa formatet för en av de lagertyper som stöds.
* The [!DNL .layer] filen måste referera till rätt sök- och dimensionsfiler, om det behövs.
* Den refererade sökfilen måste också lagras i installationskatalogen för data workbench-servern, och sökvägen måste anges korrekt i [!DNL .layer] -fil.

Mer information om format och parametrar för varje typ av lagerfil och tillhörande filer finns i avsnittet om lämplig lagertyp i det här kapitlet.
