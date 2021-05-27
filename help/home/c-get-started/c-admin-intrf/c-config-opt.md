---
description: Med alternativet Konfiguration öppnas filen Insight.cfg, som styr dina anslutningar till olika servrar.
title: Konfigurationsalternativ
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Konfigurationsalternativ{#configuration-option}

Med alternativet Konfiguration öppnas filen Insight.cfg, som styr dina anslutningar till olika servrar.

![](assets/cfg_Workstation.png)

**Så här redigerar du filen Insight.cfg**

1. Ändra parametrarna i fönstret [!DNL Insight.cfg]. Detaljerade beskrivningar av parametrarna i filen [!DNL Insight.cfg] finns i [Insight Configuration Parameters](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Om du vill spara konfigurationsinställningarna högerklickar du på **[!UICONTROL Insight.cfg (modified)]** längst upp i fönstret och klickar på **[!UICONTROL Save as Insight.cfg]**.

**Lägga till nya servrar**

1. I fönstret [!DNL Insight.cfg] högerklickar du på **[!UICONTROL Servers]** och klickar på **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Slutför eller ändra serverparametrarna för att ge Data Workbench åtkomst till den önskade servern. Detaljerade beskrivningar av parametrarna i filen [!DNL Insight.cfg] finns i [Insight Configuration Parameters](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Upprepa steg 1 och steg 2 för varje server som du vill konfigurera en anslutning till.
1. Om du vill spara konfigurationsinställningarna högerklickar du på **[!UICONTROL Insight.cfg (modified)]** längst upp i fönstret och klickar på **[!UICONTROL Save as Insight.cfg]**.

Datan Workbench försöker ansluta till servern/servrarna med de inställningar som du har angett. Om en anslutning upprättas visas en grön nod i [!DNL Servers Manager] enligt nedan. Om Datan Workbench inte kan ansluta till servern visas en röd nod.

![](assets/vis_SysStat_RedGreenDots.png)
