---
description: DPU-konfigurationsfilen DPU.cfg anger olika prestandaparametrar för Insight Server.
title: Konfigurera DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Konfigurera DPU.cfg{#configuring-dpu-cfg}

DPU-konfigurationsfilen DPU.cfg anger olika prestandaparametrar för Insight Server.

Hur du ställer in de här parametrarna beror på datauppsättningens storlek och många andra faktorer. Kontakta Adobe Consulting Services för att få hjälp med prestandajustering.

**Rekommenderad frekvens:** Endast när det behövs

**Ändra  [!DNL Insight Server] DPU-prestandainställningar**

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Insight Server] som du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. Klicka på **[!UICONTROL Components]** i [!DNL Server Files Manager] för att visa innehållet. Filen [!DNL DPU.cfg] finns i den här katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *servernamn* för [!DNL DPU.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i kolumnen [!DNL Temp] för [!DNL DPU.cfg].
1. Högerklicka på den nya bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicka på en komponent i fönstret [!DNL DPU.cfg] för att visa dess innehåll.
1. Ändra prestanda och sökvägsinställningar efter behov. En lista över tillgängliga parametrar i den här filen finns i [DPU-prestandainställningar](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Kontakta Adobe innan du ändrar någon av parametrarna i den här filen.

   ![](assets/cfg_DPU_egvalues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
