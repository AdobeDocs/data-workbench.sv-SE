---
description: Uppgraderar serverkomponenter för Data Workbench 6.1 från 5.4-installation.
title: DWB Server upgrade 5.4 to 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# DWB Server-uppgradering: 5.4 till 5.5{#dwb-server-upgrade-to}

{{eol}}

Uppgraderar serverkomponenter för Data Workbench 6.1 från 5.4-installation.

Uppgradering från [!DNL Insight] 5.4 till [!DNL Insight] 5.5 är relativt enkelt.

Du kan också uppgradera direkt från [!DNL Insight] 5.3 till [!DNL Insight] 5.5 genom att följa stegen nedan. Se till att du utför alla uppgraderingsåtgärder som listas i [Uppgradera från Insight 5.4 till 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) och [Uppgradera från Insight 5.4 till 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) -avsnitt.

1. Stoppa [!DNL Insight Server] tjänster på alla servrar i klustret utom [!DNL Insight Master Server].

   1. Kopiera nya [!DNL ReportServer.exe] och [!DNL Insight.exe] till mappen Software\Insight.

   1. Efter [!DNL Insight] klienten har uppdaterats, kopiera [!DNL InsightServer.exe] och [!DNL InsightServer64.exe] till mappen \Bin.

   1. Vänta på [!DNL Insight Master Server] till att börja med, kontrollera sedan vilken version som körs via [!DNL Connections] visualisering.

1. På klustrets [!DNL Master Server] i [!DNL Insight] klient:

   1. Skapa en lokal kopia av den befintliga [!DNL Base] och ändra namn på den (till exempel BaseBackup).
   1. Kopiera nya [!DNL Base] till mappen Profiler.
   1. Upprepa dessa två steg för mappen Transform.

1. Kopiera mappen Scripts från serverpaketet till [!DNL Master Server] till serverinstallationskatalogen.
1. Kopiera [!DNL Terrain Images.cfg.off] till mappen Komponenter i [!DNL Master Server].
   **Att uppgradera klientprogramvara från [!DNL Insight] 5.4 till 5.5**

I [!DNL Insight.cfg] filen, kontrollera att inställningen Update Software är inställd på TRUE.
