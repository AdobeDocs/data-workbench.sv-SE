---
description: Information om tidszonskoder och -format.
solution: Analytics
title: Tidszonskoder
topic: Data workbench
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tidszonskoder{#time-zone-codes}

Information om tidszonskoder och -format.

De flesta tidsbaserade parametrarna i data workbench-servern anges i följande format:

* Month DD , YYYY HH :MM :SS TZone
* Exempel: 13 augusti 2013 kl. 22.30.00 EST

Tidszoner uttrycks i ett systemoberoende tidszonsformat (Coordinated Universal Time) i följande format:

* UTC +hhm-format

Tecknet (+) kan antingen vara ett plustecken (+) eller ett minustecken (-), och det är förskjutningen från UTC i timmar och minuter. Den valfria variabeln visar en uppsättning regler för att implementera sommartid eller en liknande policy för klockbyte.

Om du anger regler måste det finnas en tabbavgränsad fil med namnet [!DNL dstrules.dst] i katalogen Dataset\TimeZone för antingen [!DNL Base] profilen (för konfigurationsfiler som inte är kopplade till en viss datauppsättning) eller datauppsättningsprofilen (för konfigurationsfiler som är datauppsättningsspecifika). Filen anger en oberoende uppsättning regler för tidszon för sommartid. Du kan ha olika regeluppsättningar för olika år. I den [!DNL DST.dst] fil som Adobe tillhandahåller i [!DNL Base] profilen specificeras de amerikanska standardreglerna som fastställs i Energy Policy Act från 2005 (som börjar 2007) och amerikanska regler för tidigare år.

Exempel på tidszonsposter visas nedan:

* Amerikansk sommartid: Tidszon = sträng: UTC -0500 DST
* UTC-tid utan förskjutning och inga dispositioner (motsvarar GMT): Tidszon = sträng: UTC -0000

När det här formatet används behöver systemtidszonen för data workbench-servern, data workbench- och rapportdatorerna inte vara samma som den angivna tidszonen. Dessutom behöver inte alla aktiva datauppsättningsprofiler på en data workbench-serverdator ha samma tidszonsinställning.

Följande tabell innehåller en lista med koder som du kan använda för att ange tidszoner i tidsbaserade parametrar.

## Tidszonskod, tabell {#section-b4f965b872c543e2ac52a3c94410d076}

Om du implementerar en policy för sommartid eller liknande klockbytesprinciper, måste du spara filen som innehåller rätt regler i katalogen för profilnamn på [!DNL .dst] [!DNL \Dataset\Timezone] datorn med data workbench-servern.

| Code | Tidszon | Förskjutning från GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| test | Eastern Standard | 5 |
| edt | Eastern Daylight | 5 |
| cst | Central standard | 6 |
| cdt | Central, dagsljus | 6 |
| mst | Mountain Standard | 7 |
| mdt | Mountain, dagsljus | 7 |
| pst | Pacific Standard | 8 |
| pdt | Pacific, dagsljus | 8 |

