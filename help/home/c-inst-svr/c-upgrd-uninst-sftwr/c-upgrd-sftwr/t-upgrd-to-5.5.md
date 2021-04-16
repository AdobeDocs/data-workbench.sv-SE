---
description: Uppgraderar serverkomponenter för Data Workbench 6.1 från 5.4-installation.
title: DWB Server upgrade 5.4 to 5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# DWB Server-uppgradering: 5,4 till 5,5{#dwb-server-upgrade-to}

Uppgraderar serverkomponenter för Data Workbench 6.1 från 5.4-installation.

Därför är det relativt enkelt att uppgradera från [!DNL Insight] 5.4 till [!DNL Insight] 5.5.

Du kan även uppgradera direkt från [!DNL Insight] 5.3 till [!DNL Insight] 5.5 genom att följa stegen nedan. Se till att du utför alla uppgraderingsuppgifter som listas i avsnittet [Uppgradera från Insight 5.4 till 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) och avsnittet [Uppgradera från Insight 5.4 till 5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9).

1. Stoppa [!DNL Insight Server]-tjänsterna på alla servrar i klustret utom för [!DNL Insight Master Server].

   1. Kopiera de nya [!DNL ReportServer.exe]- och [!DNL Insight.exe]-filerna till mappen Software\Insight.

   1. När [!DNL Insight]-klienten har uppdaterats kopierar du filerna [!DNL InsightServer.exe] och [!DNL InsightServer64.exe] till mappen \Bin.

   1. Vänta tills [!DNL Insight Master Server] har startats och kontrollera sedan vilken version som körs via visualiseringen [!DNL Connections].

1. I klustrets [!DNL Master Server] i klienten [!DNL Insight]:

   1. Skapa en lokal kopia av den befintliga [!DNL Base]-profilen och byt namn på den (till exempel BaseBackup).
   1. Kopiera den nya [!DNL Base]-profilen till mappen Profiler.
   1. Upprepa dessa två steg för mappen Transform.

1. Kopiera mappen Scripts från serverpaketet till [!DNL Master Server] till serverinstallationskatalogen.
1. Kopiera filen [!DNL Terrain Images.cfg.off] till mappen Komponenter i [!DNL Master Server].
   **Att uppgradera klientprogramvara från  [!DNL Insight] 5.4 till 5.5**

Kontrollera att inställningen Update Software är TRUE i [!DNL Insight.cfg]-filen.
