---
description: Konfigurationsfilen Communications.cfg innehåller nätverksinställningar för Insight Server och sökvägen till filen Access Control.cfg.
title: Konfigurera kommunikation
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Konfigurera kommunikation{#configuring-communications}

{{eol}}

Konfigurationsfilen Communications.cfg innehåller nätverksinställningar för Insight Server och sökvägen till filen Access Control.cfg.

De här inställningarna hjälper dig att ansluta till [!DNL Insight Server].

**Rekommenderad frekvens:** Endast vid behov

**Så här visar och ändrar du kommunikationsinställningar i[!DNL Insight]**

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Insight Server] du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL Communications.cfg] filen finns i den här katalogen.
1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn för [!DNL Communications.cfg] och klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Communications.cfg].
1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. I [!DNL Communications.cfg] fönster, klicka **[!UICONTROL component]** för att visa innehållet.
1. Ändra inställningarna efter behov. Mer information om parametrarna i den här filen finns i [Inställningar för kommunikationskonfiguration](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Steginformation](assets/cfg_communications_examplevalues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL Temp] kolumn och markera **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
