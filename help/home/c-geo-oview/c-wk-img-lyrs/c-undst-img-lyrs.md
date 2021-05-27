---
description: Konceptuell information om lager för geografiska profiler, typer av bildlager och hur du skapar nya lager.
title: Bildlager
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 0%

---

# Bildlager{#understanding-imagery-layers}

Konceptuell information om lager för geografiska profiler, typer av bildlager och hur du skapar nya lager.

## Typer av bildlager {#section-ce25364651a04cd1b83f9ac7c231fa41}

Med Data Workbench [!DNL Geography] kan du visa följande typer av bildlager i data workbench:

* **Terrängbildlager:** Den här typen av lager visar terrängbilder av jorden, över vilka geografiska data kan visas. Globens visualisering i data workbench är ett exempel på ett terrängbildslager. Se [Arbeta med terrängbildlager](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Elementpunktslager:** Den här typen av lager visar en punkt på jorden för varje element i en dimension. Se [Arbeta med elementpunktslager](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Vektorlager:** Den här typen av lager visar vektordata (konturteckningar) på jorden. Se [Arbeta med vektorlager](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

I data workbench kan du välja vilka av dessa lager du vill visa för en viss analysuppgift.

## Geografiska profillager {#section-4d9fb9b357764493a4d97d2b4068bb67}

Profilen [!DNL Geography] innehåller en uppsättning standardbildlager som lagras i mappen Profiles\Geography\Maps folder within the data workbench server installation directory:

* **Blå marmor 2 km:** Det här terrängbildslagret skapar en 3D-karta över världen, vilket är vad som visas när du lägger till den globala visualiseringen på en arbetsyta. När det här lagret inte är markerat visas inte glöden, men de andra lagren visas fortfarande. Filen [!DNL Blue Marble 2km.layer] refererar till filen [!DNL Blue Marble 2km.tsi].

   Mer information om hur du arbetar med globala visualiseringar finns i *Datans Workbench användarhandbok*.

* **Zip-punkter:** Med det här elementpunktslagret kan du mappa platser i datauppsättningen med hjälp av en ZIP-kod i USA. Uppslagsfilen [!DNL Zip Points.txt] (tillhandahålls av Adobe) innehåller en lista över alla USA:s ZIP-koder och varje ZIP-kods latitud och longitud. Filen [!DNL Zip Points.layer] refererar till filen [!DNL Zip Points.txt] och filen [!DNL Zipcode.dim] och innehåller de konfigurationsparametrar som behövs för att visa platserna i världen. Varje element i ZIP-koddimensionen ( [!DNL Zipcode.dim]) som du definierar i datauppsättningen mappas på jorden med den latitud och longitud som listas för den ZIP-koden i [!DNL Zip Points.txt]-sökfilen.

   Mer information om hur du definierar dimensioner finns i *Konfigurationshandboken för datauppsättningar.*.

* **Gränser:** Detta vektorlager ger de viktigaste politiska gränserna i världen, till exempel länder, samt gränserna för jordens naturliga fysiska egenskaper, till exempel sjöar och öar. Filen [!DNL Boundaries.layer] refererar till en eller flera av filerna [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] och [!DNL world boundaries.vec].

* **IP-koordinater:** Det här elementpunktslagret använder dynamiska punkter för att mappa platser i datauppsättningen med hjälp av IP-adresser. Filen [!DNL IP Coordinates.layer] refererar till dimensionen Koordinater ( [!DNL Coordinates.dim]) och anger Visitors-måttet som det mätvärde som ska användas för att bestämma storleken på punkterna i världen för varje koordinat.

Din [!DNL Geography]-profil eller andra profiler i din installation kan innehålla ytterligare bildlager som Adobe har tillhandahållit eller som ditt företag har skapat.

## Skapar nya lager {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Du kan skapa nya bildlager genom att kopiera lämplig typ av lagerfil som finns i [!DNL Geography]-profilen till valfri Profil\*profilnamn*\Kartor-mapp och sedan ändra namn på och redigera filen efter behov. Alla nya lager måste uppfylla följande krav:

* Filen [!DNL .layer] måste följa formatet för en av de lagertyper som stöds.
* Filen [!DNL .layer] måste referera till rätt uppslags- och dimensionsfiler, om det behövs.
* Den refererade sökfilen måste också lagras i installationskatalogen för data workbench-servern, och sökvägen måste anges korrekt i filen [!DNL .layer].

Mer information om format och parametrar för varje typ av lagerfil och tillhörande filer finns i avsnittet om lämplig lagertyp i det här kapitlet.
