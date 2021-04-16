---
description: När du skapar ett elementpunktslager som refererar till en uppslagsfil för att få latitud- och longituddata, hämtas platsen för punkten genom att varje element och dess associerade latitud och longitud hämtas från uppslagsfilen.
title: Definiera elementpunktslager som refererar till sökfiler
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
exl-id: b6928821-c825-43e2-8c7b-2ce0f49aa67e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Definiera elementpunktslager som refererar till sökfiler{#defining-element-point-layers-referencing-lookup-files}

När du skapar ett elementpunktslager som refererar till en uppslagsfil för att få latitud- och longituddata, hämtas platsen för punkten genom att varje element och dess associerade latitud och longitud hämtas från uppslagsfilen.

I stället för att använda en sökfil kan du använda funktionen [!DNL Dynamic Points], som bäddar in latitud och longitud för en plats i namnet på varje element i en dimension. Se [Definiera elementpunktslager med hjälp av dynamiska punkter](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Om du vill definiera ett elementpunktslager som refererar till en sökfil måste du skapa eller redan ha tillgång till följande:

* **En** dimension som definieras i  [!DNL Transformation.cfg] filen eller en omformningsdatauppsättning innehåller en fil. Mer information om omvandlingskonfigurationsfiler finns i *Konfigurationshandboken för datauppsättningar*.

* **En uppslagsfil** som innehåller de data som används för att rita varje datapunkt. Den här filen måste innehålla minst tre kolumner med data för varje datapunkt: nyckeln, longituden och latituden. Mer information om det format som krävs för sökfilen finns i [Elementpunktens sökfilformat](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **En** lagerfil som anger platsen för sökfilen och identifierar relaterade mått och mått samt kolumnnamnen nyckel, longitud och latitud i sökfilen. Mer information om vilket format som krävs för lagerfilen finns i [Elementpunktslagerfilformat](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Filen [!DNL Zip Points.layer], som ingår i profilen [!DNL Geography], är ett elementpunktslager som identifierar filen [!DNL Zipcode.dim], filen [!DNL Sessions.metric], uppslagsfilen [!DNL Zip Points.txt] samt namnen på kolumnerna key, longitude, latitude och name i sökfilen.
