---
description: Administrativa varningar skickar e-postmeddelanden till de angivna e-postadresserna när fel upptäcks av Insight Server under den normala åtgärden.
title: Konfigurera administrativa aviseringar
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---

# Konfigurerar administrativa aviseringar{#configuring-administrative-alerts}

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

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Insight Server] som du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. Klicka på **[!UICONTROL Components]** i [!DNL Server Files Manager] för att visa innehållet. Filen [!DNL Administrative Alerts.cfg] finns i den här katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *servernamn *för [!DNL Administrative Alerts.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i kolumnen [!DNL Temp] för [!DNL Administrative Alerts.cfg].
1. Högerklicka på den nya bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. I fönstret [!DNL Administrative Alerts.cfg] klickar du på **[!UICONTROL component]** för att visa innehållet.
1. Fyll i parametrarna efter behov. En lista över de parametrar som är tillgängliga i den här filen finns i [Konfigurationsinställningar för administrativa aviseringar](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Steginformation](assets/cfg_adminalerts_examplevalues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Valfritt) Om du arbetar i ett kluster och vill att samma administrativa varningar ska tillämpas på varje databehandlingsenhet, måste du kopiera och klistra in den uppdaterade [!DNL Administrative Alerts.cfg]-filen i [!DNL Components for Processing Servers]-mappen i den överordnad [!DNL Insight Server]-installationskatalogen.
