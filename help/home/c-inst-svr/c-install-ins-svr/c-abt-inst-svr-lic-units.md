---
description: Insight Server finns i två licenstyper.
solution: Insight
title: Om licensenheter för Insight Server
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Om licensenheter för Insight Server{#about-insight-server-license-units}

Insight Server finns i två licenstyper.

Följande två licenstyper:

* [Databehandlingsenhet (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [Filserverenhet (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Databehandlingsenhet (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

Den här typen av [!DNL Insight Server] kan bearbeta, lagra och hantera data från en Adobe-datamängd. Det kan också lagra loggfiler som innehåller källdata som datauppsättningen skapas från, eller ta emot dessa data från en [!DNL Insight Server] filserverenhet (FSU). En DPU är den typ av [!DNL Insight Server] med vilken [!DNL Insight] och [!DNL Report] klienter interagerar direkt.

Om du installerar en [!DNL Insight Server] DPU läser du [Installationsprocedurer för en Insight Server DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## Filserverenhet (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

Den här typen av server är konfigurerad för att ta emot och lagra händelsedata från en eller flera instanser av [!DNL Sensor] eller instanser av händelsereplikationer ( [!DNL Repeater] funktioner som tillhandahålls med en licens för särskild användning) och strömma data till en eller flera [!DNL Insight Server] databehandlingsenheter (DPU) för att skapa Adobe-datauppsättningar. DPU:er kommunicerar med en FSU med ett protokoll som optimerar överföringen av händelsedata till DPU och är avsevärt snabbare än att lagra loggfiler på vanliga filservrar. Användning av en FSU minskar också maskinvarukostnaderna genom att tillåta att loggdata lagras på en hårdvara till lägre kostnad och minskar den administrativa komplexiteten genom att tillåta flera stycken [!DNL Sensors] att peka på en enda [!DNL Insight Server].

Om du installerar en [!DNL Insight Server] FSU läser du [Installationsprocedurer för en Insight Server FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
