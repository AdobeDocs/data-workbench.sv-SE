---
description: Parametern Tidszon i filen Transformation.cfg styr tidsdimensioner, tidskonverteringar (t.ex. definition av fältet x-local-timestring) och formatering av alla lokala tidpunkter i datauppsättningsprofilen.
title: Tidszoner
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Tidszoner{#time-zones}

{{eol}}

Parametern Tidszon i filen Transformation.cfg styr tidsdimensioner, tidskonverteringar (t.ex. definition av fältet x-local-timestring) och formatering av alla lokala tidpunkter i datauppsättningsprofilen.

>[!NOTE]
>
>Parametern Tidszon påverkar inte funktioner på systemnivå, t.ex. tidsstämplar i status- och händelseloggar, som uttrycks i systemets lokala tid.

Parametern Time Zone har stöd för ett systemoberoende tidszonsformat (&quot;Coordinated Universal Time&quot;) i följande format:

Tidszon = sträng: UTC +hhm-format

Tecknet (+) kan vara ett plustecken (+) eller ett minustecken (-) och *htt* är förskjutningen från UTC i timmar och minuter. Den valfria variabeln *destrules* anger en uppsättning regler för att implementera sommartid eller en liknande policy för ändring av klockslag.

Om du anger *destrules*, en tabbavgränsad fil med namnet [!DNL dstrules .dst] måste finnas i datauppsättningsprofilens underkatalog Dataset\TimeZone. Filen anger en oberoende uppsättning regler för tidszon för sommartid. Du kan ha olika regeluppsättningar för olika år. The [!DNL DST.dst] den fil som Adobe tillhandahållit i basprofilen anger de amerikanska standardreglerna som fastställs i energipolicylagen från 2005 (som börjar 2007) och de amerikanska reglerna för tidigare år.

Exempel på tidszonsposter visas nedan:

* Amerikansk sommartid: Tidszon = sträng: UTC -0500 DST
* UTC-tid utan förskjutning och inga dekortecken: Tidszon = sträng: UTC -0000

När det här formatet används, systemtidszonen för data workbench-servern, data workbench och [!DNL Report] datorer behöver inte vara samma som den angivna tidszonen. Dessutom behöver inte alla aktiva datauppsättningsprofiler på en data workbench-serverdator ha samma tidszonsinställning.

Adobe rekommenderar inte att du kör mer än en datauppsättningsprofil på en enda dator med en workbench-server eller ett kluster med data workbench-servrar.

Användare av Data Workbench kommer att se data i datauppsättningsprofilens tidszon i stället för deras systemtidszon. Adobe rekommenderar att systemtidszonen för en dator med en workbench-server är densamma som tidszonen som används i dess datauppsättningar.

>[!NOTE]
>
>Du kan ange en tidszonsparameter i dialogrutan [!DNL Log Processing.cfg] -fil, där den används för tidskonverteringar under loggbearbetning. Mer information om parametern Tidszon i [!DNL Log Processing.cfg] -fil, se [Konfigurationsfil för loggbearbetning](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
