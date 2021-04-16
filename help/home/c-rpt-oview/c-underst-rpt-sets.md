---
description: En rapportuppsättning är en samling arbetsytor som genereras av Report Server baserat på de värden som anges i en Report.cfg-konfigurationsfil.
title: Rapportuppsättningar
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Rapportuppsättningar{#understanding-report-sets}

En rapportuppsättning är en samling arbetsytor som genereras av Report Server baserat på de värden som anges i en Report.cfg-konfigurationsfil.

I installationsmappen för [!DNL Insight] representerar varje undermapp i mappen &lt;*arbetsprofilnamn*>\Reports en rapportuppsättning som har skapats. Varje rapportuppsättning har en egen [!DNL Report.cfg]-konfigurationsfil i den undermappen.

>[!NOTE]
>
>I Datan Workbench [!DNL Profile Manager] visas rapportuppsättningar som undermappar i mappen [!DNL Reports]. Mer information om [!DNL Profile Manager] finns i [Datans Workbench användarhandbok](https://docs.adobe.com/content/help/en/data-workbench/using/home.html#Data_Workbench_Help).

Genom att definiera specifika konfigurationsinställningar för en rapportuppsättning i dess [!DNL Report.cfg]-fil kan du schemalägga skapandet och distributionen av rapporterna, inklusive vem som tar emot vilka rapporter och i vilka format.
