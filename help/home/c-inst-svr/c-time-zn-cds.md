---
description: Formatera instruktioner om tidsbaserade parametrar i Insight Server.
title: Tidszonskoder
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 2%

---

# Tidszonskoder{#time-zone-codes}

Formatera instruktioner om tidsbaserade parametrar i Insight Server.

De flesta tidsbaserade parametrar i [!DNL Insight Server] anges i följande format:

*Månad DD, ÅÅÅÅ HH:MM:SS TimeZone*

Exempel: 13 augusti 2013 kl. 22.30.00 EST

Tidszoner uttrycks i ett systemoberoende tidszonsformat (Coordinated Universal Time) i följande format:

UTC +htt *moduler*

Tecknet (+) kan vara ett plus- (+) eller ett minustecken (-) och *htt* är förskjutningen från UTC i timmar och minuter. Den valfria variabeln *dstrules* anger en uppsättning regler för att implementera sommartid eller en liknande klockbytespolicy.

Om du anger *moduler* måste en tabbavgränsad fil med namnet *&lt; [!DNL dstrules]>* [!DNL .dst] finnas i katalogen Dataset\TimeZone i antingen basprofilen (för konfigurationsfiler som inte är kopplade till en viss datauppsättning) eller datauppsättningsprofilen (för konfigurationsfiler som är datauppsättningsspecifika). Filen anger en oberoende uppsättning regler för tidszon för sommartid. Du kan ha olika regeluppsättningar för olika år. Filen [!DNL DST.dst] som tillhandahålls av Adobe i basprofilen anger de amerikanska standardreglerna som fastställs i energipolicylagen från 2005 (som börjar 2007) och amerikanska regler för tidigare år.

Exempel på tidszonsposter visas nedan:

* Amerikansk sommartid: Tidszon = sträng: UTC -0500 DST
* UTC-tid utan förskjutning och inga *moduler* (motsvarar GMT): Tidszon = sträng: UTC -0000

När det här formatet används behöver systemtidszonen på datorerna [!DNL Insight Server], [!DNL Insight] och [!DNL Report] inte vara samma som den angivna tidszonen. Dessutom behöver inte alla aktiva datauppsättningsprofiler på en [!DNL Insight Server]-dator ha samma tidszonsinställning.

Följande tabell innehåller en lista med koder som du kan använda för att ange tidszoner i tidsbaserade parametrar.

## Kodtabell för tidszon {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Om du implementerar en policy för sommartid eller liknande klockförflyttningsprinciper måste du spara filen [!DNL .dst] som innehåller rätt regler i *profilnamnet*\Dataset\Timezone directory on the [!DNL Insight Server]-datorn.

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
