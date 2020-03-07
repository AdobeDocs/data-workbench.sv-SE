---
description: Instruktionerna för att installera en Insight Server FSU och konfigurera den för administrativt bruk liknar de som används för att installera och konfigurera en Insight Server DPU.
solution: Insight
title: Installationsprocedurer för en Insight Server FSU
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installationsprocedurer för en Insight Server FSU{#installation-procedures-for-an-insight-server-fsu}

Instruktionerna för att installera en Insight Server FSU och konfigurera den för administrativt bruk liknar de som används för att installera och konfigurera en Insight Server DPU.

För *MS System Center Endpoint Protection* i Windows 2012-servrar måste dessa körbara filer läggas till i de **undantagna processerna:**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

Om du vill installera och konfigurera en [!DNL Insight Server] FSU måste du utföra följande uppgifter:

1. Installera [!DNL Insight Server] programfilerna.
1. Installera det [!DNL Insight Server] digitala certifikatet.
1. Kontrollera portinställningarna i [!DNL Communications.cfg] filen.
1. Ändra [!DNL Access Control.cfg] filen så att administratörsåtkomst tillåts till [!DNL the Server] från [!DNL the Client].
1. Ändra [!DNL server.address] filen för att definiera serverns nätverksplats.
1. Ange parametrar för minnesanvändning i Windows enligt beskrivningen.
1. Registrera [!DNL Insight Server] som en Windows-tjänst enligt beskrivningen.

   Instruktioner om hur du konfigurerar datakällor, behörigheter och kommunikation för en [!DNL Insight Server] FSU finns i *konfigurationsguiden* för datauppsättningar.

