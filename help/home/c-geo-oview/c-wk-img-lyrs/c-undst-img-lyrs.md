---
description: Konceptuell information om lager för geografiska profiler, typer av bildlager och hur du skapar nya lager.
solution: Analytics
title: Bildlager
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bildlager{#understanding-imagery-layers}

Konceptuell information om lager för geografiska profiler, typer av bildlager och hur du skapar nya lager.

## Typer av bildlager {#section-ce25364651a04cd1b83f9ac7c231fa41}

Med Data Workbench [!DNL Geography] kan du visa följande typer av bildlager i Data Workbench:

* **Terrängbildlager:** Den här typen av lager visar terrängbilder av jorden, över vilka geografiska data kan visas. Globens visualisering i data workbench är ett exempel på ett terrängbildslager. Se [Arbeta med terrängbildlager](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Elementpunktslager:** Den här typen av lager visar en punkt på jorden för varje element i en dimension. Se [Arbeta med elementpunktslager](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Vektorlager:** Den här typen av lager visar vektordata (konturteckningar) på jorden. Se [Arbeta med vektorlager](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

I data workbench kan du välja vilka av dessa lager du vill visa för en viss analysuppgift.

## Geografiska profillager {#section-4d9fb9b357764493a4d97d2b4068bb67}

Profilen innehåller en uppsättning [!DNL Geography] standardbildlager som lagras i mappen Profiles\Geography\Maps folder within the data workbench server installation directory:

* **Blå marmor 2 km:** Det här terrängbildslagret skapar en 3D-karta över världen, vilket är vad som visas när du lägger till globala visualiseringar på en arbetsyta. När det här lagret inte är markerat visas inte glöden, men de andra lagren visas fortfarande. Filen refererar [!DNL Blue Marble 2km.layer] till [!DNL Blue Marble 2km.tsi] filen.

   Mer information om hur du arbetar med globala visualiseringar finns i *användarhandboken* för Data Workbench.

* **Postnummer:** Med det här elementpunktslagret kan du mappa platser i datauppsättningen med hjälp av en ZIP-kod i USA. Uppslagsfilen (tillhandahålls av Adobe) innehåller en lista över alla amerikanska ZIP-koder och varje ZIP-kods latitud och longitud. [!DNL Zip Points.txt] Filen refererar [!DNL Zip Points.layer] till [!DNL Zip Points.txt] filen och [!DNL Zipcode.dim] filen och innehåller de konfigurationsparametrar som behövs för att visa platserna i världen. Varje element i ZIP-koddimensionen ( [!DNL Zipcode.dim]) som du definierar i datauppsättningen mappas på jorden med den latitud och longitud som listas för den ZIP-koden i [!DNL Zip Points.txt] sökfilen.

   Mer information om hur du definierar dimensioner finns i *Konfigurationshandboken för datauppsättningar.*

* **Gränser:** Det här vektorskiktet utgör världens största politiska gränser, till exempel länder, liksom gränserna för jordens naturliga fysiska egenskaper, till exempel sjöar och öar. Filen refererar [!DNL Boundaries.layer] till en eller flera av [!DNL mwcoast.vec]-, [!DNL mwisland.vec]-, [!DNL mwlake.vec], [!DNL mwnation.vec]-, [!DNL mwriver.vec], [!DNL mwstate.vec]- [!DNL US states.vec]och [!DNL world boundaries.vec] -filerna.

* **IP-koordinater:** I det här elementpunktslagret används dynamiska punkter för att mappa platser i datauppsättningen med hjälp av IP-adresser. Filen refererar till [!DNL IP Coordinates.layer] dimensionen Koordinater ( [!DNL Coordinates.dim]) och anger Visitors-måttet som det mätvärde som ska användas för att bestämma storleken på punkterna i världen för varje koordinat.

Din [!DNL Geography] profil eller andra profiler i din installation kan innehålla ytterligare bildlager som Adobe har tillhandahållit eller som ditt företag har skapat.

## Skapa nya lager {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Du kan skapa nya bildlager genom att kopiera lämplig typ av lagerfil som ingår i [!DNL Geography] profilen till en profilmapp\*profilnamn*\Kartor och sedan ändra namn på och redigera filen efter behov. Alla nya lager måste uppfylla följande krav:

* Filen måste [!DNL .layer] följa formatet för en av de lagertyper som stöds.
* Filen måste vid behov referera till rätt sök- och dimensionsfiler [!DNL .layer] .
* Den refererade sökfilen måste också lagras i installationskatalogen för data workbench-servern, och sökvägen måste anges korrekt i [!DNL .layer] filen.

Mer information om format och parametrar för varje typ av lagerfil och tillhörande filer finns i avsnittet om lämplig lagertyp i det här kapitlet.
