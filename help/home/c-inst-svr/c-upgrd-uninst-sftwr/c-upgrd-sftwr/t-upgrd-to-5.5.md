---
description: Uppgraderar serverkomponenter för Data Workbench 6.1 från 5.4-installation.
solution: Insight
title: DWB Server upgrade 5.4 to 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB Server-uppgradering: 5.4 till 5.5{#dwb-server-upgrade-to}

Uppgraderar serverkomponenter för Data Workbench 6.1 från 5.4-installation.

Därför är det relativt enkelt att uppgradera från [!DNL Insight] 5.4 till [!DNL Insight] 5.5.

Du kan även uppgradera direkt från [!DNL Insight] 5.3 till [!DNL Insight] 5.5 genom att följa stegen nedan. Se till att du utför alla uppgraderingsuppgifter som listas i [Uppgradera från Insight 5.4 till 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) och [Uppgradera från Insight 5.4 till 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) .

1. Stoppa [!DNL Insight Server] tjänsterna på alla servrar i klustret utom [!DNL Insight Master Server].

   1. Kopiera de nya [!DNL ReportServer.exe] och [!DNL Insight.exe] nya filerna till mappen Software\Insight.

   1. När [!DNL Insight] klienten har uppdaterat kopierar du filerna [!DNL InsightServer.exe] och [!DNL InsightServer64.exe] filerna till mappen \Bin.

   1. Vänta tills [!DNL Insight Master Server] programmet har startats och kontrollera sedan vilken version som körs via [!DNL Connections] visualiseringen.

1. På klustrets [!DNL Master Server] i [!DNL Insight] klienten:

   1. Skapa en lokal kopia av den befintliga [!DNL Base] profilen och byt namn på den (till exempel BaseBackup).
   1. Kopiera den nya [!DNL Base] profilen till mappen Profiler.
   1. Upprepa dessa två steg för mappen Transform.

1. Kopiera mappen Scripts från serverpaketet till [!DNL Master Server] installationskatalogen för Server.
1. Kopiera [!DNL Terrain Images.cfg.off] filen till mappen Komponenter i [!DNL Master Server].
   **Att uppgradera klientprogramvara från[!DNL Insight]5.4 till 5.5**

Kontrollera att inställningen Update Software är TRUE i [!DNL Insight.cfg] filen.
