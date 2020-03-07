---
description: En rapportuppsättning är en samling arbetsytor som genereras av Report Server baserat på de värden som anges i en Report.cfg-konfigurationsfil.
solution: Analytics
title: Rapportuppsättningar
topic: Data workbench
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Rapportuppsättningar{#understanding-report-sets}

En rapportuppsättning är en samling arbetsytor som genereras av Report Server baserat på de värden som anges i en Report.cfg-konfigurationsfil.

I din [!DNL Insight] installationsmapp representerar varje undermapp i mappen &lt;*arbetsprofilnamn*>\Reports en rapportuppsättning som har skapats. Varje rapportuppsättning har en egen [!DNL Report.cfg] konfigurationsfil i den undermappen.

>[!NOTE]
>
>I [!DNL Profile Manager] Data Workbench visas rapportuppsättningar som undermappar i [!DNL Reports] mappen. Mer information om [!DNL Profile Manager]finns i [användarhandboken](https://docs.adobe.com/content/help/en/data-workbench/using/home.html#Data_Workbench_Help)för Data Workbench.

Genom att definiera specifika konfigurationsinställningar för en rapportuppsättning i dess [!DNL Report.cfg] fil kan du schemalägga skapandet och distributionen av rapporterna, inklusive vem som tar emot vilka rapporter och i vilka format.
