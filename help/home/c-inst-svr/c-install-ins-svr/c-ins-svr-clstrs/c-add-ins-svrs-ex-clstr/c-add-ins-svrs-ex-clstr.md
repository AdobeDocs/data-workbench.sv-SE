---
description: I vissa fall kanske du tycker att det är nödvändigt att lägga till en Insight Server-dator i ett befintligt Insight Server-kluster.
title: Lägga till insight-servrar i ett befintligt kluster
uuid: 951bd6fe-14e4-4192-917c-342fde7b43ba
exl-id: 9845c13b-781c-43e9-aaa1-e31418c93ef0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# Lägga till insight-servrar i ett befintligt kluster{#adding-insight-servers-to-an-existing-cluster}

{{eol}}

I vissa fall kanske du tycker att det är nödvändigt att lägga till en Insight Server-dator i ett befintligt Insight Server-kluster.

När du lägger till en [!DNL Insight Server] DPU eller [!DNL Insight Server] FSU till ett kluster måste uppdatera konfigurationsfilerna på överordnad [!DNL Insight Server] för att inkludera adressinformationen för de nya datorerna och konfigurera den nya DPU eller FSU.

>[!NOTE]
>
>Processerna som beskrivs i detta avsnitt kräver [!DNL Insight]. Om du inte har installerat [!DNL Insight]följer du instruktionerna i [!DNL Insight] Användarhandbok* innan du fortsätter.
