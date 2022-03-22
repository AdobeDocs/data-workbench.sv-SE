---
description: Formatera instruktioner om tidsbaserade parametrar i Insight Server.
title: Tidszonskoder (Insight Server)
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Tidszonskoder{#time-zone-codes}

Formatera instruktioner om tidsbaserade parametrar i Insight Server.

De flesta tidsbaserade parametrarna i [!DNL Insight Server] anges i följande format:

*DD månad, ÅÅÅÅ HH:MM:Tidszon*

Exempel: 13 augusti 2013 22:30:00 EST

Tidszoner uttrycks i ett systemoberoende tidszonsformat (Coordinated Universal Time) i följande format:

UTC +htt *destrules*

Tecknet (+) kan vara ett plustecken (+) eller ett minustecken (-) och *htt* är förskjutningen från UTC i timmar och minuter. Den valfria variabeln *destrules* anger en uppsättning regler för att implementera sommartid eller en liknande policy för ändring av klockslag.

Om du anger *destrules*, en tabbavgränsad fil med namnet *&lt; [!DNL dstrules]>* [!DNL .dst] måste finnas i katalogen Dataset\TimeZone för antingen basprofilen (för konfigurationsfiler som inte är kopplade till en viss datauppsättning) eller datauppsättningsprofilen (för konfigurationsfiler som är datauppsättningsspecifika). Filen anger en oberoende uppsättning regler för tidszon för sommartid. Du kan ha olika regeluppsättningar för olika år. The [!DNL DST.dst] den fil som Adobe tillhandahållit i basprofilen anger de amerikanska standardreglerna som fastställs i energipolicylagen från 2005 (som börjar 2007) och de amerikanska reglerna för tidigare år.

Exempel på tidszonsposter visas nedan:

* Amerikansk sommartid: Tidszon = sträng: UTC -0500 DST
* UTC-tid utan förskjutning och ingen *destrules* (motsvarar GMT): Tidszon = sträng: UTC -0000

När det här formatet används är systemtidszonen för [!DNL Insight Server], [!DNL Insight]och [!DNL Report] datorer behöver inte vara samma som den angivna tidszonen. Dessutom finns alla aktiva datauppsättningsprofiler på en [!DNL Insight Server] datorn behöver inte ha samma tidszonsinställning.

Följande tabell innehåller en lista med koder som du kan använda för att ange tidszoner i tidsbaserade parametrar.

## Tidszonskod, tabell {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Om du implementerar en policy för sommartid eller liknande policy för ändring av klockslag måste du spara [!DNL .dst] fil som innehåller lämpliga regler i *profilnamn*\DataSet\Timezone directory på [!DNL Insight Server] dator.

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
