---
description: Administrativa varningar skickar e-postmeddelanden till de angivna e-postadresserna när fel upptäcks av Insight Server under den normala åtgärden.
solution: Analytics
title: Konfigurera administrativa aviseringar
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---


# Konfigurera administrativa aviseringar{#configuring-administrative-alerts}

Administrativa varningar skickar e-postmeddelanden till de angivna e-postadresserna när fel upptäcks av Insight Server under den normala åtgärden.

**Rekommenderad frekvens:** Före produktion

>[!NOTE]
>
>Användningen av administrativa varningar kräver att [!DNL Insight Server] har åtkomst till en vidarebefordrande SMTP-server för att skicka varningar via e-post.

Mottagarna av e-postmeddelanden bör vara nyckelpersoner inom systemadministration och primära intressenter.

Filen Administrativa aviseringar, [!DNL Administrative Alerts.cfg], används för att konfigurera administrativa aviseringar för [!DNL Insight Server].

>[!NOTE]
>
>Om du kör ett kluster måste du skapa eller ändra aviseringar på överordnad [!DNL Insight Server] i klustret.

**Skapa eller ändra en administrativ varning**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för det [!DNL Insight Server] du vill konfigurera och klicka sedan på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL Administrative Alerts.cfg] katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *servernamn *för [!DNL Administrative Alerts.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Administrative Alerts.cfg].
1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicka i [!DNL Administrative Alerts.cfg] fönstret **[!UICONTROL component]** för att visa innehållet.
1. Fyll i parametrarna efter behov. En lista över de parametrar som är tillgängliga i den här filen finns i Konfigurationsinställningar för [administrativa aviseringar](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Steginformation](assets/cfg_adminalerts_examplevalues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Valfritt) Om du arbetar i ett kluster och vill att samma administrativa varningar ska gälla för varje databehandlingsenhet, måste du kopiera och klistra in den uppdaterade [!DNL Administrative Alerts.cfg] filen i [!DNL Components for Processing Servers] mappen i den överordnad [!DNL Insight Server] installationskatalogen.
