---
description: Med tjänsten Insight ServerReplication kan du överföra händelsedata som samlats in och lagrats på en Insight Server-dator till en annan Insight Server-dator.
title: Installera replikeringstjänsten
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 0%

---

# Installera replikeringstjänsten{#installing-the-replication-service}

{{eol}}

Med tjänsten Insight ServerReplication kan du överföra händelsedata som samlats in och lagrats på en Insight Server-dator till en annan Insight Server-dator.

Vanligtvis är den dator där data samlas in och lagras konfigurerad att köras som en [!DNL Repeater] dator. Se [Repeaterfunktioner](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). The [!DNL Replication Service], som konfigureras av [!DNL Replicate.cfg] fil, aktiverar [!DNL Insight Server] dator för att hämta data från [!DNL Repeater] datorn och lagra den lokalt. The [!DNL Insight Server] datorn kallas måldator. Flera [!DNL Insight Server] DPU:er kan ansluta till en enda [!DNL Repeater] att begära kopior av händelsedata för att kunna inkluderas i flera datauppsättningar.

Du kan använda [!DNL Replication Service] i nätverksinfrastrukturer med flera lager av brandväggar för att uppnå kommunikation med en port till en port mellan komponenter som separeras av brandväggar.

**Så här installerar du[!DNL Replication Service]**

The [!DNL Replicate.cfg] filen ska installeras som en del av [!DNL Insight Server] installation. Du kan hitta filen i [!DNL Components] din mapp [!DNL Insight Server] installationskatalog. Om du inte har den här filen kontaktar du Adobe.
