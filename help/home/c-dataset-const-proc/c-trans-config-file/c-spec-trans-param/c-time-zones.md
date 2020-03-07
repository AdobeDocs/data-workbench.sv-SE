---
description: Parametern Tidszon i filen Transformation.cfg styr tidsdimensioner, tidskonverteringar (t.ex. definition av fältet x-local-timestring) och formatering av alla lokala tidpunkter i datauppsättningsprofilen.
solution: Analytics
title: Tidszoner
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Tidszoner{#time-zones}

Parametern Tidszon i filen Transformation.cfg styr tidsdimensioner, tidskonverteringar (t.ex. definition av fältet x-local-timestring) och formatering av alla lokala tidpunkter i datauppsättningsprofilen.

>[!NOTE]
>
>Parametern Tidszon påverkar inte funktioner på systemnivå, t.ex. tidsstämplar i status- och händelseloggar, som uttrycks i systemets lokala tid.

Parametern Time Zone har stöd för ett systemoberoende tidszonsformat (&quot;Coordinated Universal Time&quot;) i följande format:

Tidszon = sträng: UTC +hhm-format

Tecknet (+) kan vara ett plus- (+) eller ett minustecken (-), och *tt* är förskjutningen från UTC i timmar och minuter. Den valfria variabeln *visar* en uppsättning regler för att implementera sommartid eller en liknande policy för klockbyte.

Om du anger *regler* måste det finnas en tabbavgränsad fil med namnet [!DNL dstrules .dst] i datauppsättningsprofilens underkatalog Dataset\TimeZone. Filen anger en oberoende uppsättning regler för tidszon för sommartid. Du kan ha olika regeluppsättningar för olika år. I den [!DNL DST.dst] fil som Adobe tillhandahåller i basprofilen anges de amerikanska standardreglerna som fastställs i Energy Policy Act från 2005 (som börjar 2007) och amerikanska regler för tidigare år.

Exempel på tidszonsposter visas nedan:

* Amerikansk sommartid: Tidszon = sträng: UTC -0500 DST
* UTC-tid utan förskjutning och inga dekortecken: Tidszon = sträng: UTC -0000

När det här formatet används behöver systemtidszonen för data workbench-servern, data workbench och [!DNL Report] datorer inte vara samma som den angivna tidszonen. Dessutom behöver inte alla aktiva datauppsättningsprofiler på en data workbench-serverdator ha samma tidszonsinställning.

Adobe rekommenderar inte att du kör mer än en datauppsättningsprofil på en enda dator för en workbench-server eller på ett kluster för en data workbench-server.

Användare av Data Workbench kommer att se data i datauppsättningsprofilens tidszon i stället för deras systemtidszon. Adobe rekommenderar att systemtidszonen för en dator med en workbench-server är densamma som tidszonen som används i dess datamängder.

>[!NOTE]
>
>Du kan ange en tidszonsparameter i [!DNL Log Processing.cfg] filen, där den används för tidskonverteringar under loggbearbetning. Mer information om parametern Tidszon i [!DNL Log Processing.cfg] filen finns i [Loggbearbetningskonfigurationsfil](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

