---
description: Med tjänsten Insight ServerReplication kan du överföra händelsedata som samlats in och lagrats på en Insight Server-dator till en annan Insight Server-dator.
title: Installera replikeringstjänsten
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 0%

---

# Installera replikeringstjänsten{#installing-the-replication-service}

Med tjänsten Insight ServerReplication kan du överföra händelsedata som samlats in och lagrats på en Insight Server-dator till en annan Insight Server-dator.

Vanligtvis är den dator där data samlas in och lagras konfigurerad att köras som en [!DNL Repeater]-dator. Se [Repeaterfunktionalitet](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). [!DNL Replication Service], som konfigureras av filen [!DNL Replicate.cfg], gör att en [!DNL Insight Server]-dator kan hämta data från [!DNL Repeater]-datorn och lagra den lokalt. [!DNL Insight Server]-datorn kallas måldator. Flera [!DNL Insight Server] DPU:er kan ansluta till en enda [!DNL Repeater] för att begära kopior av händelsedata för inkludering i flera datamängder.

Du kan använda [!DNL Replication Service] i nätverksinfrastrukturer med flera lager av brandväggar för att få kommunikation mellan komponenter som avgränsas av brandväggar med en port och en port.

**Så här installerar du[!DNL Replication Service]**

[!DNL Replicate.cfg]-filen ska installeras som en del av din [!DNL Insight Server]-installation. Du hittar filen i mappen [!DNL Components] i installationskatalogen för [!DNL Insight Server]. Om du inte har den här filen kontaktar du Adobe.
