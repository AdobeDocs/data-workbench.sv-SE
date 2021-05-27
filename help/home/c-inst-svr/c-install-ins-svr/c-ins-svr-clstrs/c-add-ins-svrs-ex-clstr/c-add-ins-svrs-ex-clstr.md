---
description: I vissa fall kanske du tycker att det är nödvändigt att lägga till en Insight Server-dator i ett befintligt Insight Server-kluster.
title: Lägga till insight-servrar i ett befintligt kluster
uuid: 951bd6fe-14e4-4192-917c-342fde7b43ba
exl-id: 9845c13b-781c-43e9-aaa1-e31418c93ef0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# Lägga till insiktsservrar i ett befintligt kluster{#adding-insight-servers-to-an-existing-cluster}

I vissa fall kanske du tycker att det är nödvändigt att lägga till en Insight Server-dator i ett befintligt Insight Server-kluster.

När du lägger till en [!DNL Insight Server] DPU eller [!DNL Insight Server] FSU i ett kluster måste du uppdatera konfigurationsfilerna på överordnad [!DNL Insight Server] så att de innehåller adressinformationen för de nya datorerna och ställa in den nya DPU eller FSU.

>[!NOTE]
>
>Processerna som beskrivs i det här avsnittet kräver [!DNL Insight]. Om du inte har installerat [!DNL Insight] följer du instruktionerna i användarhandboken * [!DNL Insight]* innan du fortsätter.
