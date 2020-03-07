---
description: Med tjänsten Insight ServerReplication kan du överföra händelsedata som samlats in och lagrats på en Insight Server-dator till en annan Insight Server-dator.
solution: Insight
title: Installera replikeringstjänsten
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installera replikeringstjänsten{#installing-the-replication-service}

Med tjänsten Insight ServerReplication kan du överföra händelsedata som samlats in och lagrats på en Insight Server-dator till en annan Insight Server-dator.

Vanligtvis är den dator där data samlas in och lagras konfigurerad att köras som en [!DNL Repeater] dator. Se [Repeaterfunktioner](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). Med [!DNL Replication Service]den, som konfigureras av [!DNL Replicate.cfg] filen, kan en [!DNL Insight Server] dator hämta data från [!DNL Repeater] datorn och lagra dem lokalt. Datorn kallas [!DNL Insight Server] måldator. Flera [!DNL Insight Server] DPU:er kan ansluta till en enda för [!DNL Repeater] att begära kopior av händelsedata för inkludering i flera datauppsättningar.

Du kan använda [!DNL Replication Service] i nätverksinfrastrukturer med flera lager av brandväggar för att uppnå kommunikation med en port till en port mellan komponenter som separeras av brandväggar.

**Så här installerar du[!DNL Replication Service]**

Filen ska [!DNL Replicate.cfg] installeras som en del av [!DNL Insight Server] installationen. Du kan hitta filen i [!DNL Components] mappen för din [!DNL Insight Server] installationskatalog. Om du inte har den här filen kontaktar du Adobe.
