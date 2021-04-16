---
description: Kontrollera om sändaren körs genom att ställa in varningar, kontrollera systemstatusen för sensorn med mera.
title: Bekräfta att dataöverföringen körs
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# Bekräfta att dataöverföringen körs{#confirming-that-the-data-transmitter-is-running}

Kontrollera om sändaren körs genom att ställa in varningar, kontrollera systemstatusen för sensorn med mera.

**Rekommenderad frekvens:** var 5-10:e minut

* [Kontrollera att sändningsprocessen körs.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Konfigurera administrativa varningar i Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Kontrollera systemstatusen för sensorn.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Kontrollerar överföringsprocessen {#section-79806fa3b7034a8eaf571a66e24874d7}

Ett sätt att verifiera att sändaren körs är att kontrollera att [!DNL Sensor]-sändningsprocessen körs på varje webbserver där en [!DNL Sensor]-instans är installerad. Sändningsprocessen visas som&quot;txlogd&quot; i webbserverns lista över processer. Du kan utföra den här kontrollen med ett systemövervakningsverktyg.

## Ställa in administrativa aviseringar på Data Workbench-servern {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Ett annat sätt att verifiera att sändaren körs är att skapa automatiska administrativa varningar i [!DNL data workbench server]. När administrativa aviseringar har konfigurerats genererar [!DNL data workbench server] en e-postavisering när den inte har fått några data från en konfigurerad och tidigare ansluten [!DNL Sensor] inom den tidsram som anges i parametern [!DNL Sensor] Alert Timeout (min) i [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg]-filen. Mer information om hur du konfigurerar administrativa varningar finns i *Installations- och administrationshandboken för serverprodukter*.

## Kontrollera systemstatusen för sensorn {#section-de9d7e359242487a9fbead4ed65aebbc}

Ett annat sätt att verifiera att sändaren körs är att kontrollera [!DNL Servers Manager] i Datan Workbench manuellt.

**Så här visar du[!DNL Servers Manager]**

* Högerklicka i Data Workbench på en arbetsyta, klicka på **[!UICONTROL Admin]** och klicka sedan på **[!UICONTROL Servers]** under [!DNL Manage].

Om ikonen för en [!DNL Sensor] är grön körs sändaren.

Mer information om [!DNL Servers Manager] finns i kapitlet Administrativa gränssnitt i *Datan Workbench [!DNL Sensor] Guide*.
