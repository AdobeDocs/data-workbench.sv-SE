---
description: Insight Server finns i två licenstyper.
title: Om licensenheter för Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# Om licensenheter för Insight Server{#about-insight-server-license-units}

{{eol}}

Insight Server finns i två licenstyper.

Följande två licenstyper:

* [Databehandlingsenhet (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Filserverenhet (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Databehandlingsenhet (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Den här typen av [!DNL Insight Server] kan bearbeta, lagra och hantera data från en datauppsättning i Adobe. Det kan också lagra loggfilerna som innehåller källdata som datauppsättningen skapas från, eller så kan det ta emot dessa data från en [!DNL Insight Server] Filserverenhet (FSU). En DPU är typen av [!DNL Insight Server] som [!DNL Insight] och [!DNL Report] kunderna interagerar direkt.

Om du installerar en [!DNL Insight Server] DPU, se [Installationsprocedurer för en Insight Server DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## Filserverenhet (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Den här typen av server är konfigurerad för att ta emot och lagra händelsedata från en eller flera [!DNL Sensor] eller händelsedatareplikeringsinstanser ( [!DNL Repeater] med en licens för särskild användning) och strömma data till en eller flera [!DNL Insight Server] Databehandlingsenheter (DPU) för att skapa datauppsättningar i Adobe. DPU:er kommunicerar med en FSU med ett protokoll som optimerar överföringen av händelsedata till DPU och är avsevärt snabbare än att lagra loggfiler på vanliga filservrar. Användning av en FSU minskar också maskinvarukostnaderna genom att tillåta att loggdata lagras på en hårdvara till lägre kostnad och minskar den administrativa komplexiteten genom att tillåta flera [!DNL Sensors] för att peka på en [!DNL Insight Server].

Om du installerar en [!DNL Insight Server] FSU, se [Installationsprocedurer för en Insight Server FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
