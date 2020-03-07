---
description: Händelsedata måste säkerhetskopieras dagligen med företagets vanliga säkerhetskopieringssystem och rutiner för återställning efter haveri.
solution: Insight
title: Säkerhetskopiera händelsedata
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Säkerhetskopiera händelsedata{#backing-up-event-data}

Händelsedata måste säkerhetskopieras dagligen med företagets vanliga säkerhetskopieringssystem och rutiner för återställning efter haveri.

**Rekommenderad frekvens:** Dagligen

[!DNL Insight Server] börjar med nya loggfiler kl. 12.00 GMT dagligen. Adobe rekommenderar att du säkerhetskopierar loggfiler varje dag kort efter kl. 12.00 GMT så att du kan hämta alla data från föregående dag. Om du till exempel säkerhetskopierar alla loggfiler kl. 12.05 GMT den 15 december hämtas alla data från den 14 december. [!DNL Insight Server] behöver inte stoppas vid säkerhetskopiering av loggfiler och alla funktioner är fortfarande tillgängliga.

## Säkerhetskopiera integrering, operativsystem, utdata och systemdata {#section-217e52a99f944d8e83a3cc98f3d06e7e}

**Rekommenderad frekvens:** Dagligen

Integrering, operativsystem, utdata och systemdata måste säkerhetskopieras regelbundet och med försiktighet med företagets vanliga system för säkerhetskopiering och katastrofåterställning.
