---
description: Parametern Unlock i en användares Insight.cfg-fil anger om användaren har behörighet att tillfälligt låsa upp låsta arbetsytor för redigering.
title: Ange parametern unlock
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Ange parametern unlock{#set-the-unlock-parameter}

{{eol}}

Parametern Unlock i en användares Insight.cfg-fil anger om användaren har behörighet att tillfälligt låsa upp låsta arbetsytor för redigering.

Om parametern Unlock redan finns i användarens [!DNL Insight.cfg] kan du redigera parametern med Data Workbench. Om den inte redan finns i användarens [!DNL Insight.cfg] måste du lägga till den i filen med en textredigerare, till exempel Anteckningar.

**Ange en befintlig [!DNL Unlock] parameter i filen Insight.cfg**

1. Högerklicka på en arbetsyta **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. The [!DNL Insight.cfg] filen öppnas.
1. För parametern Unlock skriver du true eller false. True gör att användaren tillfälligt kan låsa upp en låst arbetsyta medan false inte gör det.
1. Om du vill spara konfigurationsändringarna högerklickar du **[!UICONTROL Insight.cfg (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save as Insight.cfg]**.

**Lägga till parametern Unlock i filen Insight.cfg**

1. Navigera till Datans Workbench installationskatalog och öppna [!DNL Insight.cfg] med en textredigerare, t.ex. Anteckningar.
1. Lägg till parametern Unlock i slutet av filen, som i följande exempel:

[!DNL Unlock = bool: false]

1. Ange värdet som true eller false. True gör att användaren tillfälligt kan låsa upp en låst arbetsyta medan false inte gör det.
1. Spara och stäng filen.
