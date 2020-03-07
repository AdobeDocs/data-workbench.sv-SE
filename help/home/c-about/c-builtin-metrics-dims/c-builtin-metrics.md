---
description: Data workbench innehåller inbyggda mätvärden.
solution: Analytics
title: Inbyggda mätvärden
topic: Data workbench
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Inbyggda mätvärden{#built-in-metrics}

Data workbench innehåller inbyggda mätvärden.

I följande tabell visas de tillgängliga inbyggda mätvärdena för data workbench:

| Inbyggda mätvärden | Beskrivning |
|---|---|
| Från | Datamängdens storlek i 100 nanosekunder sedan 1 januari 1600 00:00 UTC. Tidsstämpeln Efter är den senaste gången i datauppsättningen för vilken alla data definitivt har bearbetats. |
| Lästa loggbyte | Den totala mängden komprimerade data (i byte) som hittills har bearbetats under loggbearbetningsfasen. |
| Totalt antal loggbyte | Den totala mängden komprimerade data (i byte) i loggfiler som matchar de konfigurerade loggkällorna och datasetens start- och slutdatumintervall. Om loggbearbetningen har pausats i konfigurationsfilen för loggbehandlingsläge är Totalt antal loggbyte detsamma som Läs loggbyte. |
| Loggbehandlingens förlopp | Procentuellt slutförande av loggbearbetningsfasen för Insight Server-databearbetning. |
| Totalt antal avkodade loggposter | Antalet poster i loggfilerna som har avkodats som en del av loggbearbetningsfasen för Insight Server-databearbetning. |
| Totalt antal filtrerade loggposter | Antalet poster i loggfilerna som accepterats av robotfiltret efter avkodningen samt loggpostvillkoren och andra filter som används som en del av loggbearbetningsfasen för databearbetning i Insight Server. |
| Totalt antal loggposter | Antalet poster i loggfilerna som hittills har bearbetats i loggbearbetningsfasen för Insight Server-databearbetning. |
| Totalt antal bearbetade loggposter | Antalet filtrerade loggposter som har integrerats i Adobe-datauppsättningen. |
| Transformeringsförlopp | Procentandelen slutförda transformeringsfasen för databearbetning i Insight Server. |
| Okomprimerade loggbyte lästa | Den totala mängden okomprimerade data (i byte) som hittills har bearbetats under loggbearbetningsfasen. |
