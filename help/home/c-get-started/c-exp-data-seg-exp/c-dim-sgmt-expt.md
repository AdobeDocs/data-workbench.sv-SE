---
description: Alla data som du vill exportera måste definieras som en dimension i profilen.
solution: Analytics
title: Skapa dimensioner för segmentexport
topic: Data workbench
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skapa dimensioner för segmentexport{#create-dimensions-for-use-with-segment-export}

Alla data som du vill exportera måste definieras som en dimension i profilen.

Om dimensionen inte redan finns i profilen måste du skapa den. Du kan skapa dimensioner på något av följande sätt:

* Lägg till en dimension till [!DNL Transformation.cfg] filen. Se *Konfigurationshandboken* för datauppsättningar.

* Skapa en ny [!DNL .dim] fil. Se [Skapa och redigera härledda dimensioner](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Gör markeringar i en visualisering, t.ex. en processkarta eller ett segment, och spara markeringarna som en dimension. Se [Spara dimensioner från processkartor](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) och [Skapa segmentdimensioner](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

När du exporterar ett datafält som spårnings-ID eller e-postadress (som kan innehålla många element) måste du skapa en normal dimension som lagrar rådatasträngarna.

Mer information om denorala dimensioner finns i konfigurationsguiden för *datauppsättningar*.
