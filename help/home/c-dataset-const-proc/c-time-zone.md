---
description: Information om tidszonskoder och -format.
title: Koder och format för tidszon
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 2%

---

# Tidszonskoder{#time-zone-codes}

{{eol}}

Information om tidszonskoder och -format.

De flesta tidsbaserade parametrarna i data workbench-servern anges i följande format:

* Month DD , YYYY HH :MM :SS TZone
* Exempel: 13 augusti 2013 22:30:00 EST

Tidszoner uttrycks i ett systemoberoende tidszonsformat (Coordinated Universal Time) i följande format:

* UTC +hhm-format

Tecknet (+) kan antingen vara ett plustecken (+) eller ett minustecken (-), och det är förskjutningen från UTC i timmar och minuter. Den valfria variabeln visar en uppsättning regler för att implementera sommartid eller en liknande policy för klockbyte.

Om du anger tabeller är det en tabbavgränsad fil med namnet [!DNL dstrules.dst] måste finnas i katalogen Dataset\TimeZone i [!DNL Base] profil (för konfigurationsfiler som inte är kopplade till en viss datauppsättning) eller datauppsättningsprofilen (för konfigurationsfiler som är datauppsättningsspecifika). Filen anger en oberoende uppsättning regler för tidszon för sommartid. Du kan ha olika regeluppsättningar för olika år. The [!DNL DST.dst] som tillhandahålls av Adobe i [!DNL Base] profilen anger de amerikanska standardregler som fastställs i 2005 års energipolicylag (som börjar 2007) och USA:s regler för tidigare år.

Exempel på tidszonsposter visas nedan:

* Amerikansk sommartid: Tidszon = sträng: UTC -0500 DST
* UTC-tid utan förskjutning och inga dispositioner (motsvarar GMT): Tidszon = sträng: UTC -0000

När det här formatet används behöver systemtidszonen för data workbench-servern, data workbench- och rapportdatorerna inte vara samma som den angivna tidszonen. Dessutom behöver inte alla aktiva datauppsättningsprofiler på en data workbench-serverdator ha samma tidszonsinställning.

Följande tabell innehåller en lista med koder som du kan använda för att ange tidszoner i tidsbaserade parametrar.

## Tidszonskod, tabell {#section-b4f965b872c543e2ac52a3c94410d076}

Om du implementerar en policy för sommartid eller liknande policy för ändring av klockslag måste du spara [!DNL .dst] fil som innehåller rätt regler i profilnamnet [!DNL \Dataset\Timezone] på data workbench-serverdatorn.

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
