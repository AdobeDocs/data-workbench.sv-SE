---
description: Med alternativet Konfiguration öppnas filen Insight.cfg, som styr dina anslutningar till olika servrar.
solution: Analytics
title: Konfigurationsalternativ
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurationsalternativ{#configuration-option}

Med alternativet Konfiguration öppnas filen Insight.cfg, som styr dina anslutningar till olika servrar.

![](assets/cfg_Workstation.png)

**Så här redigerar du filen Insight.cfg**

1. Ändra parametrarna i [!DNL Insight.cfg] fönstret efter behov. Detaljerade beskrivningar av parametrarna i [!DNL Insight.cfg] filen finns i [Insight Configuration Parameters](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Om du vill spara konfigurationsinställningarna högerklickar du **[!UICONTROL Insight.cfg (modified)]** högst upp i fönstret och klickar på **[!UICONTROL Save as Insight.cfg]**.

**Lägga till nya servrar**

1. Högerklicka i [!DNL Insight.cfg] fönstret **[!UICONTROL Servers]** och klicka **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Slutför eller ändra serverparametrarna för att ge Data Workbench åtkomst till den önskade servern. Detaljerade beskrivningar av parametrarna i [!DNL Insight.cfg] filen finns i [Insight Configuration Parameters](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Upprepa steg 1 och steg 2 för varje server som du vill konfigurera en anslutning till.
1. Om du vill spara konfigurationsinställningarna högerklickar du **[!UICONTROL Insight.cfg (modified)]** högst upp i fönstret och klickar på **[!UICONTROL Save as Insight.cfg]**.

Data Workbench försöker ansluta till servern/servrarna med de inställningar du har angett. Om en anslutning upprättas visas en grön nod i [!DNL Servers Manager] enligt nedan. Om Data Workbench inte kan ansluta till servern visas en röd nod.

![](assets/vis_SysStat_RedGreenDots.png)

