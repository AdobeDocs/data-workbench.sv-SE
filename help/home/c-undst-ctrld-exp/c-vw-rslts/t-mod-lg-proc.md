---
description: Du måste lägga till x-experimentfältet i filen Log Processing.cfg, som används för att skapa en utökad dimension.
solution: Insight,Analytics
title: Ändra Log Processing.cfg
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändra Log Processing.cfg{#modifying-log-processing-cfg}

Du måste lägga till x-experimentfältet i filen Log Processing.cfg, som används för att skapa en utökad dimension.

Se [Ändra Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Så här ändrar du Log Processing.cfg**

1. I [!DNL Insight]öppnar du [!DNL Profile Manager] genom att högerklicka på en arbetsyta och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** eller genom att öppna arbetsytan Profilhantering på [!DNL Admin] fliken.
1. Klicka på [!DNL Profile Manager]för **[!UICONTROL Dataset]** att visa innehållet.
1. Högerklicka på bockmarkeringen bredvid [!DNL Log Processing.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret [!DNL Log Processing.cfg] visas.
1. Klicka **[!UICONTROL Fields]** för att visa innehållet.
1. Högerklicka på det sista fältet i den aktuella listan och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Skriv x-experiment i det nya fältet, som i följande exempel:

   ![Steginformation](assets/logprocessing.png)

1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.
1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen för [!DNL Log Processing.cfg] i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* för att spara de lokalt gjorda ändringarna i arbetsprofilen.

   >[!NOTE]
   >
   >Datauppsättningen börjar ombearbetas omedelbart.

   Mer information om loggbearbetning och fält finns i konfigurationsguiden för *datauppsättningar*.

