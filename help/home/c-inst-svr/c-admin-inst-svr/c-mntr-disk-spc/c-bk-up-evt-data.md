---
description: Händelsedata måste säkerhetskopieras dagligen med företagets vanliga säkerhetskopieringssystem och rutiner för återställning efter haveri.
title: Säkerhetskopiera händelsedata
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Säkerhetskopiera händelsedata{#backing-up-event-data}

Händelsedata måste säkerhetskopieras dagligen med företagets vanliga säkerhetskopieringssystem och rutiner för återställning efter haveri.

**Rekommenderad frekvens:** varje dag

[!DNL Insight Server] börjar med nya loggfiler kl. 12.00 GMT dagligen. Adobe rekommenderar att du säkerhetskopierar loggfiler varje dag kort efter kl. 12.00 GMT så att du kan hämta alla data från föregående dag. Om du till exempel säkerhetskopierar alla loggfiler kl. 12.05 GMT den 15 december hämtas alla data från den 14 december. [!DNL Insight Server] behöver inte stoppas vid säkerhetskopiering av loggfiler och alla funktioner är fortfarande tillgängliga.

## Säkerhetskopiera integrering, operativsystem, utdata och systemdata {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Rekommenderad frekvens:** varje dag

Integrering, operativsystem, utdata och systemdata måste säkerhetskopieras regelbundet och med försiktighet med företagets vanliga system för säkerhetskopiering och katastrofåterställning.
