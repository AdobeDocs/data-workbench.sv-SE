---
description: Instruktionerna för att installera en Insight Server FSU och konfigurera den för administrativt bruk liknar de som används för att installera och konfigurera en Insight Server DPU.
title: Installationsprocedurer för en Insight Server FSU
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Installationsprocedurer för en Insight Server FSU{#installation-procedures-for-an-insight-server-fsu}

Instruktionerna för att installera en Insight Server FSU och konfigurera den för administrativt bruk liknar de som används för att installera och konfigurera en Insight Server DPU.

För *MS System Center Endpoint Protection* på Windows 2012-servrar måste dessa körbara filer läggas till i **Exkluderade processer:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Om du vill installera och konfigurera en [!DNL Insight Server] FSU måste du utföra följande uppgifter:

1. Installera [!DNL Insight Server]-programfilerna.
1. Installera det digitala [!DNL Insight Server]-certifikatet.
1. Kontrollera portinställningarna i filen [!DNL Communications.cfg].
1. Ändra [!DNL Access Control.cfg]-filen så att administrativ åtkomst till [!DNL the Server] från [!DNL the Client] tillåts.
1. Ändra [!DNL server.address]-filen för att definiera serverns nätverksplats.
1. Ange parametrar för minnesanvändning i Windows enligt beskrivningen.
1. Registrera [!DNL Insight Server] som en Windows-tjänst enligt beskrivningen.

   Instruktioner om hur du konfigurerar datakällor, behörigheter och kommunikation för en [!DNL Insight Server] FSU finns i *Konfigurationshandboken för datauppsättningar*.
