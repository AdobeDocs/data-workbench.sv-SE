---
description: DPU-konfigurationsfilen DPU.cfg anger olika prestandaparametrar för Insight Server.
title: Konfigurera DPU.cfg
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Konfigurera DPU.cfg{#configuring-dpu-cfg}

{{eol}}

DPU-konfigurationsfilen DPU.cfg anger olika prestandaparametrar för Insight Server.

Hur du ställer in de här parametrarna beror på datauppsättningens storlek och många andra faktorer. Kontakta Adobe Consulting Services för att få hjälp med prestandajustering.

**Rekommenderad frekvens:** Endast vid behov

**Ändra [!DNL Insight Server] Inställningar för DPU-prestanda**

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Insight Server] du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL DPU.cfg] filen finns i den här katalogen.
1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn för [!DNL DPU.cfg] och klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL DPU.cfg].
1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. I [!DNL DPU.cfg] klickar du på komponenten för att visa dess innehåll.
1. Ändra prestanda och sökvägsinställningar efter behov. En lista med tillgängliga parametrar i den här filen finns i [Inställningar för DPU-prestanda](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >Kontakta Adobe innan du ändrar någon av parametrarna i den här filen.

   ![](assets/cfg_DPU_egvalues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL Temp] kolumn och markera **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
