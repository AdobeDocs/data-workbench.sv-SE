---
description: Ett fältvisningsprogram är en tabell som innehåller värdena för ett eller flera datafält.
solution: Analytics
title: Fältvisningsprogram
topic: Data workbench
uuid: 1227b0de-6ae8-4f97-ad3e-5c9ead818ba5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Fältvisningsprogram{#field-viewer}

Ett fältvisningsprogram är en tabell som innehåller värdena för ett eller flera datafält.

De fält vars värden visas är indata eller utdata från en datamängds loggkällor, omformningar eller utökade dimensioner. Fältets namn visas i kolumnrubriken och varje rad innehåller fältets värde för en enda rad med källdata. Eftersom fältvisningsprogram gör det möjligt att se ett fälts värden, är de användbara när du skriver och testar [reguljära uttryck](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

Du kan öppna ett fältvisningsprogram som en bildtext från en [!DNL Transformation Dependency] karta eller som en fristående visualisering på [!DNL Admin] menyn:

* Skapa ett fältvisningsprogram från en [!DNL Transformation Dependency] karta. När du öppnar ett fältvisningsprogram från en [!DNL Transformation Dependency] karta fylls visningsprogrammet i automatiskt baserat på loggkällan, omformningen eller dimensionen som du högerklickar på. För en loggkälla eller en omformning är fälten i visningsprogrammet indata eller utdata från loggkällan eller omformningen. För en dimension är fälten indata för dimensionen. Du kan lägga till och ta bort fält efter behov.

* Skapa ett fältvisningsprogram som en fristående visualisering. När du öppnar ett fältvisningsprogram som en fristående visualisering kan du skapa en [!DNL Log Processing Field Viewer] eller en [!DNL Transformation Field Viewer]. Visningsprogrammet är tomt och du måste lägga till önskade fält i visningsprogrammet. För en [!DNL Log Processing Field Viewer]fil kan du lägga till fält från [!DNL Log Processing.cfg] filen eller valfri [!DNL Log Processing Dataset Include] fil. För en [!DNL Transformation Field Viewer]fil kan du lägga till fält från [!DNL Transformation.cfg] filen eller valfri [!DNL Transformation Dataset Include] fil.

![](assets/vis_FieldViewer_OneField.png)

>[!NOTE]
>
>Fältvisningsprogram är inte tabellvisualiseringar. Därför har de inte de egenskaper som är associerade med tabeller.

Mer information om hur du lägger till och tar bort fält och filtrerar i ett fältvisningsprogram finns i [Administrativa gränssnitt](../../../../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).
