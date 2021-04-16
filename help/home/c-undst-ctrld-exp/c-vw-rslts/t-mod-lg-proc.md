---
description: Du måste lägga till x-experimentfältet i filen Log Processing.cfg, som används för att skapa en utökad dimension.
solution: Analytics,Analytics
title: Ändra Log Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Ändrar Log Processing.cfg{#modifying-log-processing-cfg}

Du måste lägga till x-experimentfältet i filen Log Processing.cfg, som används för att skapa en utökad dimension.

Se [Ändra Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Så här ändrar du Log Processing.cfg**

1. I [!DNL Insight] öppnar du [!DNL Profile Manager] genom att högerklicka i en arbetsyta och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, eller genom att öppna arbetsytan Profilhantering på fliken [!DNL Admin].
1. Klicka på **[!UICONTROL Dataset]** i [!DNL Profile Manager] för att visa innehållet.
1. Högerklicka på bockmarkeringen bredvid [!DNL Log Processing.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret [!DNL Log Processing.cfg] visas.
1. Klicka på **[!UICONTROL Fields]** för att visa innehållet.
1. Högerklicka på det sista fältet i den aktuella listan och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Skriv x-experiment i det nya fältet, som i följande exempel:

   ![Steginformation](assets/logprocessing.png)

1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. Högerklicka på bockmarkeringen för [!DNL Log Processing.cfg] i kolumnen [!DNL User] och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* för att spara de lokalt gjorda ändringarna i arbetsprofilen.[!DNL Profile Manager]

   >[!NOTE]
   >
   >Datauppsättningen börjar ombearbetas omedelbart.

   Mer information om loggbearbetning och fält finns i *Konfigurationshandboken för datauppsättningar*.
