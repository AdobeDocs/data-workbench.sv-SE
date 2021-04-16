---
description: Datan Workbench kan konfigureras så att endast vissa användare kan ändra vissa arbetsytor.
title: Konfigurera en låst arbetsyta
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# Konfigurera en låst arbetsyta{#configure-a-locked-workspace}

Datan Workbench kan konfigureras så att endast vissa användare kan ändra vissa arbetsytor.

När en arbetsyta är låst kan användare göra markeringar i de flesta visualiseringar och sortera data i tabeller, men kan inte ändra arbetsytan på något annat sätt. Den här funktionen förhindrar användare att göra oavsiktliga ändringar i arbetsytorna.

Följande tre element fungerar tillsammans för att styra låsning av arbetsytor:

* **En mapp.lock- eller  *arbetsytans namn*.lock-fil:** En  [!DNL folder.lock] fil anger om arbetsytorna i en viss mapp är låsta, medan en  [!DNL name.lock] arbetsytefil anger om en viss arbetsyta är låst.

* **Parametern Lås upp i en användares  [!DNL Insight.cfg] fil:** Den här parametern anger om användaren tillfälligt kan låsa upp låsta arbetsytor.
* **Menyalternativet Upplås tillfälligt:** När parametern Lås upp i användarens  [!DNL Insight.cfg] är inställd på true visas det här alternativet automatiskt på namnlistermenyn i varje låst arbetsyta så att användaren kan låsa upp den.

Mer information om [!DNL folder.lock]- och arbetsytans [!DNL name.lock]-filer finns i följande avsnitt. Mer information om hur du ställer in parametern Unlock finns i [Ange parametern Unlock](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Mer information om alternativet [!DNL Temporarily Unlock menu] finns i [Lås upp en arbetsyta](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
