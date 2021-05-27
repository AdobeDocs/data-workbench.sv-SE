---
description: Du måste se till att datorerna där Adobe-serverprodukter är installerade uppfyller de lägsta systemkraven som definieras i dokumentet för systemkrav.
title: Bekräfta att dina system är felfria
uuid: 6d132865-36ab-40fc-be24-e031f356fce2
exl-id: 543f7592-dd3c-47ba-b174-5f12e9586378
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 0%

---

# Bekräfta att dina system är felfria{#confirming-your-systems-are-healthy}

Du måste se till att datorerna där Adobe-serverprodukter är installerade uppfyller de lägsta systemkraven som definieras i dokumentet för systemkrav.

**Rekommenderad frekvens:** var 5-10:e minut

Du måste också övervaka dina system enligt bästa praxis för att hantera den aktuella maskinvaran, inklusive, men inte begränsat till, att övervaka följande:

* CPU-användning
* Diskutrymme
* Maskinvarusystemmeddelanden
* Intern systemtemperatur
* Minnesanvändning
* Strömförsörjningsförhållanden
* Prestanda och fel för RAID- eller diskstyrenhet

Adobe rekommenderar att du konfigurerar hanteringsverktyget så att du varnar administratörer när en systemparameter på en serverdator överskrider det angivna tröskelvärdet.

För [!DNL Insight Server]-datorer rekommenderar Adobe också att du konfigurerar varje [!DNL Insight Server] så att det anger när den minimala mängden diskutrymme som du har angett uppnås. Mer information om dessa varningar finns i [Konfigurera administrativa varningar](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa).
