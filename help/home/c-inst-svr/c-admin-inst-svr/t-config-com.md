---
description: Konfigurationsfilen Communications.cfg innehåller nätverksinställningar för Insight Server och sökvägen till filen Access Control.cfg.
solution: Analytics
title: Konfigurera kommunikation
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Konfigurera kommunikation{#configuring-communications}

Konfigurationsfilen Communications.cfg innehåller nätverksinställningar för Insight Server och sökvägen till filen Access Control.cfg.

De här inställningarna hjälper dig att ansluta till [!DNL Insight Server].

**Rekommenderad frekvens:** Endast vid behov

**Så här visar och ändrar du kommunikationsinställningar i[!DNL Insight]**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för det [!DNL Insight Server] du vill konfigurera och klicka sedan på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL Communications.cfg] katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* för [!DNL Communications.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Communications.cfg].
1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicka i [!DNL Communications.cfg] fönstret **[!UICONTROL component]** för att visa innehållet.
1. Ändra inställningarna efter behov. Mer information om de parametrar som är tillgängliga i den här filen finns i [Kommunikationskonfigurationsinställningar](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Steginformation](assets/cfg_communications_examplevalues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

