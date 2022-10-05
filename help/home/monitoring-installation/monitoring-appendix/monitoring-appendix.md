---
description: I det här dokumentet beskrivs profilerna med de fält, dimensioner och mått som används av Data Workbench Monitoring Profile.
title: Dimensioner och mått för Datans Workbench profil
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Dimensioner och mått för Datans Workbench profil{#data-workbench-profile-dimensions-and-metrics}

{{eol}}

I det här dokumentet beskrivs profilerna med de fält, dimensioner och mått som används av Data Workbench Monitoring Profile.

För att övervaka data workbench-servrar samlas data in med hjälp av ett skript som tolkar den detaljerade statusen samtidigt som viss serverinformation hämtas. Data workbench-serverinformation skickas sedan till ett sidtaggsanrop för data workbench Sensor för att samla in och spara i en VSL fil.

## Profiler som används av Datans Workbench övervakningsprofil {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Dessa profiler tillhandahåller mått och mätvärden som gör att du kan visa serverstatus och prestandadata:

* [Dimensioner i statusprofilen för insight-profilen](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensioner i Insight Server-statusprofilen](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensioner i Insight History-profilen](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Mätvärden i profilen för historisk övervakning av insikt](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Med statusprofilerna kan du se hur data workbench för närvarande fungerar ur ett funktionellt perspektiv. The **Profilstatus** och **Serverstatus** samlar in data från Detaljerad status och data workbench-servrarna. Alla insamlade data placeras i `cs-uri-query` fält som ska användas.

The **Historiska profiler** gör att du kan bedöma påverkan av konfigurations- och maskinvaruändringar med hjälp av historiska data. Den historiska profilen kan vara den mest användbara eftersom den gör det möjligt att bedöma hur konfigurationen och maskinvaruändringarna påverkas över tiden.
