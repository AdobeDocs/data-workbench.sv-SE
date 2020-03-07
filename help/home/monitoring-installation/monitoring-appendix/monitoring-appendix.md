---
description: I det här dokumentet beskrivs profilerna med de fält, dimensioner och mått som används av Data Workbench Monitoring Profile.
solution: Analytics
title: Profildimensioner och mått för Data Workbench
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profildimensioner och mått för Data Workbench{#data-workbench-profile-dimensions-and-metrics}

I det här dokumentet beskrivs profilerna med de fält, dimensioner och mått som används av Data Workbench Monitoring Profile.

För att övervaka data workbench-servrar samlas data in med hjälp av ett skript som tolkar den detaljerade statusen samtidigt som viss serverinformation hämtas. Data workbench-serverinformation skickas sedan till ett sidtaggsanrop för data workbench Sensor för att samla in och spara till en VSL-fil.

## Profiler som används av Data Workbench Monitoring Profile {#section-b5b1234f55c3407dae8e68b031b7cd7f}

Dessa profiler tillhandahåller mått och mätvärden som gör att du kan visa serverstatus och prestandadata:

* [Dimensioner i profilen för insight-profilstatus](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimensioner i Insight Server-statusprofilen](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimensioner i Insight History-profilen](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Mätvärden i profilen för historisk övervakning av insikt](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

Med statusprofilerna kan du se hur data workbench för närvarande fungerar ur ett funktionellt perspektiv. Profilens **statusprofil** och **serverstatusprofilen** samlar in data från Detaljerad status och data workbench-servrarna. Alla insamlade data placeras i `cs-uri-query` fältet för användning.

Med hjälp av de **historiska profilerna** kan du bedöma effekten av konfigurations- och maskinvaruändringar med hjälp av historiska data. Den historiska profilen kan vara den mest användbara eftersom den gör det möjligt att bedöma hur konfigurationen och maskinvaruändringarna påverkas över tiden.
