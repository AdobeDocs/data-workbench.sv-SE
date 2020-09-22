---
description: DPU-konfigurationsfilen DPU.cfg anger olika prestandaparametrar för Insight Server.
solution: Analytics
title: Konfigurera DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---


# Konfigurera DPU.cfg{#configuring-dpu-cfg}

DPU-konfigurationsfilen DPU.cfg anger olika prestandaparametrar för Insight Server.

Hur du ställer in de här parametrarna beror på datauppsättningens storlek och många andra faktorer. Kontakta Adobe Consulting Services för att få hjälp med prestandajustering.

**Rekommenderad frekvens:** Endast vid behov

**Så här ändrar du[!DNL Insight Server]DPU-prestandainställningar**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för det [!DNL Insight Server] du vill konfigurera och klicka sedan på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL DPU.cfg] katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* för [!DNL DPU.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL DPU.cfg].
1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicka på komponenten i [!DNL DPU.cfg] fönstret för att visa dess innehåll.
1. Ändra prestanda och sökvägsinställningar efter behov. En lista över de parametrar som är tillgängliga i den här filen finns i [DPU-prestandainställningar](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Kontakta Adobe innan du ändrar någon av parametrarna i den här filen.

   ![](assets/cfg_DPU_egvalues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

