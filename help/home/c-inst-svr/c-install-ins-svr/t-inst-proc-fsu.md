---
description: Instruktionerna för att installera en Insight Server FSU och konfigurera den för administrativt bruk liknar de som används för att installera och konfigurera en Insight Server DPU.
title: Installationsprocedurer för en Insight Server FSU
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Installationsprocedurer för en Insight Server FSU{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

Instruktionerna för att installera en Insight Server FSU och konfigurera den för administrativt bruk liknar de som används för att installera och konfigurera en Insight Server DPU.

För *MS System Center Endpoint Protection* i Windows 2012-servrar måste dessa körbara filer läggas till i **Exkluderade processer:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Installera och konfigurera [!DNL Insight Server] FSU, du måste utföra följande uppgifter:

1. Installera [!DNL Insight Server] programfiler.
1. Installera [!DNL Insight Server] digitalt certifikat.
1. Kontrollera portinställningarna i dialogrutan [!DNL Communications.cfg] -fil.
1. Ändra [!DNL Access Control.cfg] fil som ger administrativ åtkomst till [!DNL the Server] från [!DNL the Client].
1. Ändra [!DNL server.address] för att definiera serverns nätverksplats.
1. Ange parametrar för minnesanvändning i Windows enligt beskrivningen.
1. Registrera [!DNL Insight Server] som en Windows-tjänst enligt beskrivningen.

   Anvisningar om hur du konfigurerar datakällor, behörigheter och kommunikation för en [!DNL Insight Server] FSU, se *Konfigurationshandbok för datauppsättning*.
