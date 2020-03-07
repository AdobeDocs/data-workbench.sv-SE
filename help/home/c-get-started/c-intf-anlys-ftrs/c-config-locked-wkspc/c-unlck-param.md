---
description: Parametern Unlock i en användares Insight.cfg-fil anger om användaren har behörighet att tillfälligt låsa upp låsta arbetsytor för redigering.
solution: Analytics
title: Ange parametern unlock
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ange parametern unlock{#set-the-unlock-parameter}

Parametern Unlock i en användares Insight.cfg-fil anger om användaren har behörighet att tillfälligt låsa upp låsta arbetsytor för redigering.

Om parametern Lås upp redan finns i användarens [!DNL Insight.cfg] fil kan du redigera parametern med Data Workbench. Om den inte redan finns i användarens [!DNL Insight.cfg] fil måste du lägga till den i filen med en textredigerare, till exempel Anteckningar.

**Så här anger du en befintlig[!DNL Unlock]parameter i filen Insight.cfg**

1. Högerklicka **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]** på en arbetsyta. Filen [!DNL Insight.cfg] öppnas.
1. För parametern Unlock skriver du true eller false. True gör att användaren tillfälligt kan låsa upp en låst arbetsyta medan false inte gör det.
1. Om du vill spara konfigurationsändringarna högerklickar du **[!UICONTROL Insight.cfg (modified)]** längst upp i fönstret och klickar på **[!UICONTROL Save as Insight.cfg]**.

**Lägga till parametern Unlock i filen Insight.cfg**

1. Navigera till installationskatalogen för Data Workbench och öppna [!DNL Insight.cfg] filen med en textredigerare, till exempel Anteckningar.
1. Lägg till parametern Unlock i slutet av filen, som i följande exempel:

[!DNL Unlock = bool: false]

1. Ange värdet som true eller false. True gör att användaren tillfälligt kan låsa upp en låst arbetsyta medan false inte gör det.
1. Spara och stäng filen.

