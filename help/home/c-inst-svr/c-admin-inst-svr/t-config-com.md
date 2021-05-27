---
description: Konfigurationsfilen Communications.cfg innehåller nätverksinställningar för Insight Server och sökvägen till filen Access Control.cfg.
title: Konfigurera kommunikation
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Konfigurerar kommunikation{#configuring-communications}

Konfigurationsfilen Communications.cfg innehåller nätverksinställningar för Insight Server och sökvägen till filen Access Control.cfg.

De här inställningarna hjälper dig att ansluta till [!DNL Insight Server].

**Rekommenderad frekvens:** Endast när det behövs

**Så här visar och ändrar du kommunikationsinställningar i[!DNL Insight]**

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Insight Server] som du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. Klicka på **[!UICONTROL Components]** i [!DNL Server Files Manager] för att visa innehållet. Filen [!DNL Communications.cfg] finns i den här katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *servernamn* för [!DNL Communications.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i kolumnen [!DNL Temp] för [!DNL Communications.cfg].
1. Högerklicka på den nya bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. I fönstret [!DNL Communications.cfg] klickar du på **[!UICONTROL component]** för att visa innehållet.
1. Ändra inställningarna efter behov. Mer information om de parametrar som är tillgängliga i den här filen finns i [Inställningar för kommunikationskonfiguration](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Steginformation](assets/cfg_communications_examplevalues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
