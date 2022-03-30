---
description: Du måste lägga till x-experimentfältet i filen Log Processing.cfg, som används för att skapa en utökad dimension.
solution: Analytics
title: Ändra Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Ändra Log Processing.cfg{#modifying-log-processing-cfg}

Du måste lägga till x-experimentfältet i filen Log Processing.cfg, som används för att skapa en utökad dimension.

Se [Modifying Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Så här ändrar du Log Processing.cfg**

1. I [!DNL Insight]öppnar du [!DNL Profile Manager] genom att högerklicka på en arbetsyta och klicka **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** eller genom att öppna arbetsytan Profilhantering på [!DNL Admin] -fliken.
1. I [!DNL Profile Manager], klicka **[!UICONTROL Dataset]** för att visa innehållet.
1. Högerklicka på bockmarkeringen bredvid [!DNL Log Processing.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. The [!DNL Log Processing.cfg] visas.
1. Klicka **[!UICONTROL Fields]** för att visa innehållet.
1. Högerklicka på det sista fältet i den aktuella listan och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Skriv x-experiment i det nya fältet, som i följande exempel:

   ![Steginformation](assets/logprocessing.png)

1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. I [!DNL Profile Manager], högerklicka på bockmarkeringen för [!DNL Log Processing.cfg] i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* om du vill spara de lokalt gjorda ändringarna i arbetsprofilen.

   >[!NOTE]
   >
   >Datauppsättningen börjar ombearbetas omedelbart.

   Mer information om loggbearbetning och fält finns i *Konfigurationshandbok för datauppsättning*.
