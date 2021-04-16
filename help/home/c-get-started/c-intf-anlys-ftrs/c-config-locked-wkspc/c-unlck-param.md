---
description: Parametern Unlock i en användares Insight.cfg-fil anger om användaren har behörighet att tillfälligt låsa upp låsta arbetsytor för redigering.
title: Ange parametern unlock
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Ange parametern för upplåsning{#set-the-unlock-parameter}

Parametern Unlock i en användares Insight.cfg-fil anger om användaren har behörighet att tillfälligt låsa upp låsta arbetsytor för redigering.

Om parametern Unlock redan finns i användarens [!DNL Insight.cfg]-fil kan du redigera parametern med Data Workbench. Om den inte redan finns i användarens [!DNL Insight.cfg]-fil måste du lägga till den i filen med en textredigerare, till exempel Anteckningar.

**Ställa in en befintlig  [!DNL Unlock] parameter i filen Insight.cfg**

1. Högerklicka på **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]** i en arbetsyta. Filen [!DNL Insight.cfg] öppnas.
1. För parametern Unlock skriver du true eller false. True gör att användaren tillfälligt kan låsa upp en låst arbetsyta medan false inte gör det.
1. Om du vill spara konfigurationsändringarna högerklickar du **[!UICONTROL Insight.cfg (modified)]** högst upp i fönstret och klickar på **[!UICONTROL Save as Insight.cfg]**.

**Lägga till parametern Unlock i filen Insight.cfg**

1. Navigera till installationskatalogen för Datan Workbench och öppna filen [!DNL Insight.cfg] med en textredigerare, till exempel Anteckningar.
1. Lägg till parametern Unlock i slutet av filen, som i följande exempel:

[!DNL Unlock = bool: false]

1. Ange värdet som true eller false. True gör att användaren tillfälligt kan låsa upp en låst arbetsyta medan false inte gör det.
1. Spara och stäng filen.
