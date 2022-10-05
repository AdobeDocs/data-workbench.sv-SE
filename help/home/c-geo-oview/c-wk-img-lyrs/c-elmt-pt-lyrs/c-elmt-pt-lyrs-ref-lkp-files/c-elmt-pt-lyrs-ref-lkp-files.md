---
description: När du skapar ett elementpunktslager som refererar till en sökfil för att få latitud- och longituddata, hämtas platsen för punkten genom att varje element och dess associerade latitud och longitud hämtas från sökfilen.
title: Definiera elementpunktslager som refererar till sökfiler
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Definiera elementpunktslager som refererar till sökfiler{#defining-element-point-layers-referencing-lookup-files}

{{eol}}

När du skapar ett elementpunktslager som refererar till en sökfil för att få latitud- och longituddata, hämtas platsen för punkten genom att varje element och dess associerade latitud och longitud hämtas från sökfilen.

I stället för att använda en uppslagsfil kan du använda [!DNL Dynamic Points] som bäddar in latitud och longitud för en plats i namnet på varje element i en dimension. Se [Definiera elementpunktslager med hjälp av dynamiska punkter](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Om du vill definiera ett elementpunktslager som refererar till en sökfil måste du skapa eller redan ha tillgång till följande:

* **En dimension** definieras i [!DNL Transformation.cfg] eller en inkluderingsfil för en transformeringsdatauppsättning. Mer information om omvandlingskonfigurationsfiler finns i *Konfigurationshandbok för datauppsättning*.

* **En sökfil** som innehåller de data som används för att rita varje datapunkt. Den här filen måste innehålla minst tre kolumner med data för varje datapunkt: nyckeln, longituden och latituden. Mer information om vilket format som krävs för sökfilen finns i [Sökfilformat för elementpunkt](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **En lagerfil** som anger platsen för sökfilen och identifierar relaterade mått och mått samt nyckel-, longitud- och latitudkolumnnamn i sökfilen. Mer information om vilket format lagerfilen ska ha finns i [Filformat för elementpunktslager](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>The [!DNL Zip Points.layer] fil, som tillhandahålls med [!DNL Geography] profil, är ett elementpunktslager som identifierar [!DNL Zipcode.dim] -filen, [!DNL Sessions.metric] -filen, [!DNL Zip Points.txt] sökfilen och namnen på kolumnerna key, longitud, latitude och name i sökfilen.
