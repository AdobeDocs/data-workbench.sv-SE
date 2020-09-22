---
description: Kontrollera om sändaren körs genom att ställa in varningar, kontrollera systemstatusen för sensorn med mera.
solution: Analytics
title: Bekräfta att dataöverföringen körs
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---


# Bekräfta att dataöverföringen körs{#confirming-that-the-data-transmitter-is-running}

Kontrollera om sändaren körs genom att ställa in varningar, kontrollera systemstatusen för sensorn med mera.

**Rekommenderad frekvens:** Var 5-10:e minut

* [Kontrollera att sändningsprocessen körs.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Konfigurera administrativa varningar i Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Kontrollera systemstatusen för sensorn.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Kontrollera överföringsprocessen {#section-79806fa3b7034a8eaf571a66e24874d7}

Ett sätt att verifiera att sändaren körs är att kontrollera att [!DNL Sensor] sändningsprocessen körs på varje webbserver där en [!DNL Sensor] instans är installerad. Sändningsprocessen visas som&quot;txlogd&quot; i webbserverns lista över processer. Du kan utföra den här kontrollen med ett systemövervakningsverktyg.

## Konfigurera administrativa aviseringar på Data Workbench Server {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Ett annat sätt att verifiera att sändaren körs är att skapa automatiska administrativa varningar i [!DNL data workbench server]. När administrativa varningar har konfigurerats genererar [!DNL data workbench server] guiden en e-postavisering när den inte har fått några data från en konfigurerad och tidigare ansluten [!DNL Sensor] inom den tidsram som anges i parametern [!DNL Sensor] Aviseringstimeout (min) i [!DNL data workbench server’s][!DNL Administrative Alerts.cfg] filen. Mer information om hur du ställer in administrativa varningar finns i *Server Products Installation and Administration Guide*.

## Kontrollera systemstatusen för sensorn {#section-de9d7e359242487a9fbead4ed65aebbc}

Ett annat sätt att verifiera att sändaren körs är att kontrollera [!DNL Servers Manager] Datan Workbench manuellt.

**Så här visar du[!DNL Servers Manager]**

* I Data Workbench högerklickar du på en arbetsyta, klickar **[!UICONTROL Admin]** och sedan under [!DNL Manage]klickar du **[!UICONTROL Servers]**.

Om ikonen för en [!DNL Sensor] är grön körs sändaren.

Mer information om [!DNL Servers Manager]finns i kapitlet Administrativa gränssnitt i *Data Workbench[!DNL Sensor]Guide*.
