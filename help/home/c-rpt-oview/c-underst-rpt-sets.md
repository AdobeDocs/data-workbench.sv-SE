---
description: En rapportuppsättning är en samling arbetsytor som genereras av Report Server baserat på de värden som anges i en Report.cfg-konfigurationsfil.
title: Rapportuppsättningar
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Rapportuppsättningar{#understanding-report-sets}

{{eol}}

En rapportuppsättning är en samling arbetsytor som genereras av Report Server baserat på de värden som anges i en Report.cfg-konfigurationsfil.

I [!DNL Insight] installationsmapp, varje undermapp i &lt;*arbetsprofilsnamn*>\Reports-mappen representerar en rapportuppsättning som har skapats. Varje rapportuppsättning har en egen [!DNL Report.cfg] i den undermappen.

>[!NOTE]
>
>I [!DNL Profile Manager] i Data Workbench visas rapportuppsättningar som undermappar i [!DNL Reports] mapp. Mer information om [!DNL Profile Manager], se [Användarhandbok för Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html#Data_Workbench_Help).

Genom att definiera specifika konfigurationsinställningar för en rapportuppsättning i dess [!DNL Report.cfg] kan du schemalägga framtagning och distribution av rapporterna, inklusive vem som tar emot rapporter och i vilka format.
