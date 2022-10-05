---
description: Datan Workbench kan konfigureras så att endast vissa användare kan ändra vissa arbetsytor.
title: Konfigurera en låst arbetsyta
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 0%

---

# Konfigurera en låst arbetsyta{#configure-a-locked-workspace}

{{eol}}

Datan Workbench kan konfigureras så att endast vissa användare kan ändra vissa arbetsytor.

När en arbetsyta är låst kan användare göra markeringar i de flesta visualiseringar och sortera data i tabeller, men kan inte ändra arbetsytan på något annat sätt. Den här funktionen förhindrar användare att göra oavsiktliga ändringar i arbetsytorna.

Följande tre element fungerar tillsammans för att styra låsning av arbetsytor:

* **En folder.lock eller *arbetsytans namn*.lock-fil:** A [!DNL folder.lock] anger om arbetsytorna i en viss mapp är låsta, medan en arbetsyta [!DNL name.lock] anger om en viss arbetsyta är låst.

* **Parametern Lås upp i en användares [!DNL Insight.cfg] fil:** Den här parametern anger om användaren tillfälligt kan låsa upp låsta arbetsytor.
* **Menyalternativet Upplås tillfälligt:** När parametern Unlock i användarens [!DNL Insight.cfg] är inställt på true, visas det här alternativet automatiskt på namnlisten i varje låst arbetsyta för att ge användaren möjlighet att låsa upp den.

Mer information om [!DNL folder.lock] och arbetsyta [!DNL name.lock] -filer, se följande avsnitt. Mer information om hur du ställer in parametern Unlock finns i [Ange upplåsningsparameter](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Mer information om [!DNL Temporarily Unlock menu] alternativ, se [Låsa upp en arbetsyta](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
