---
description: Data Workbench kan konfigureras så att endast vissa användare kan ändra vissa arbetsytor.
solution: Analytics
title: Konfigurera en låst arbetsyta
topic: Data workbench
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera en låst arbetsyta{#configure-a-locked-workspace}

Data Workbench kan konfigureras så att endast vissa användare kan ändra vissa arbetsytor.

När en arbetsyta är låst kan användare göra markeringar i de flesta visualiseringar och sortera data i tabeller, men kan inte ändra arbetsytan på något annat sätt. Den här funktionen förhindrar användare att göra oavsiktliga ändringar i arbetsytorna.

Följande tre element fungerar tillsammans för att styra låsning av arbetsytor:

* **En mapp.lock- eller *arbetsytans namn*.lock-fil:** En [!DNL folder.lock] fil anger om arbetsytorna i en viss mapp är låsta, medan en [!DNL name.lock] arbetsytefil anger om en viss arbetsyta är låst.

* **Parametern Lås upp i en användares[!DNL Insight.cfg]fil:** Den här parametern anger om användaren tillfälligt kan låsa upp låsta arbetsytor.
* **Menyalternativet Upplås tillfälligt:** När parametern Lås upp i användarens [!DNL Insight.cfg] är inställd på true visas det här alternativet automatiskt på namnlisten i varje låst arbetsyta för att ge användaren möjlighet att låsa upp den.

Mer information om [!DNL folder.lock] arbetsytans [!DNL name.lock] filer finns i följande avsnitt. Mer information om hur du ställer in parametern Unlock finns i [Ställa in parametern](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)Unlock. Mer information om [!DNL Temporarily Unlock menu] alternativet finns i [Låsa upp en arbetsyta](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
