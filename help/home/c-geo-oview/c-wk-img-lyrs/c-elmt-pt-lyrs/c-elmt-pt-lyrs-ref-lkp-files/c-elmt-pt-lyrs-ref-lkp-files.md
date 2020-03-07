---
description: När du skapar ett elementpunktslager som refererar till en sökfil för att få latitud- och longituddata, hämtas platsen för punkten genom att varje element och dess associerade latitud och longitud hämtas från sökfilen.
solution: Analytics
title: Definiera elementpunktslager som refererar till sökfiler
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definiera elementpunktslager som refererar till sökfiler{#defining-element-point-layers-referencing-lookup-files}

När du skapar ett elementpunktslager som refererar till en sökfil för att få latitud- och longituddata, hämtas platsen för punkten genom att varje element och dess associerade latitud och longitud hämtas från sökfilen.

I stället för att använda en sökfil kan du använda [!DNL Dynamic Points] funktionen, som bäddar in latitud och longitud för en plats i namnet på varje element i en dimension. Se [Definiera elementpunktslager med hjälp av dynamiska punkter](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

Om du vill definiera ett elementpunktslager som refererar till en sökfil måste du skapa eller redan ha tillgång till följande:

* **En dimension** som är definierad i [!DNL Transformation.cfg] filen eller en transformeringsdatauppsättning innehåller fil. Mer information om omvandlingskonfigurationsfiler finns i *konfigurationsguiden* för datauppsättningar.

* **En uppslagsfil** som innehåller de data som används för att rita varje datapunkt. Den här filen måste innehålla minst tre kolumner med data för varje datapunkt: nyckeln, longituden och latituden. Mer information om det format som krävs för sökfilen finns i [Elementpunktens sökfilformat](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121).

* **En lagerfil** som anger platsen för sökfilen och identifierar relaterade mått och mått samt nyckel-, longitud- och latitudkolumnsnamn i sökfilen. Mer information om det format som behövs för lagerfilen finns i [Elementpunktslagerfilformat](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Den [!DNL Zip Points.layer] fil som finns med i [!DNL Geography] profilen är ett elementpunktslager som identifierar [!DNL Zipcode.dim] filen, [!DNL Sessions.metric] filen, [!DNL Zip Points.txt] uppslagsfilen och namnen på nycklar, longitud, latitud och namnkolumner i uppslagsfilen.

