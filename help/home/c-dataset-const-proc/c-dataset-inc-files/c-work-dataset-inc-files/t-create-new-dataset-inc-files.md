---
description: Steg för att skapa en ny inkluderingsfil för datauppsättningen.
title: Skapar en ny datauppsättning med inkluderade filer
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# Skapar en ny datauppsättning som innehåller filer{#creating-new-dataset-include-files}

Steg för att skapa en ny inkluderingsfil för datauppsättningen.

Du bör skapa en ny datauppsättningsinkluderingsfil för att kunna utföra följande konfigurationsåtgärder för datauppsättningar:

* Ange nya fält med data som ska skickas från loggbearbetning till omvandling.
* Definiera omformningar som gör något av följande:

   * Uppdatera befintliga loggfält.
   * Skapa nya fält som ska skickas från loggbearbetning till omvandling eller som används för att definiera utökade dimensioner.

      Mer information om tillgängliga omformningstyper finns i [Dataomformningar](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Om du definierar omformningar i en ny datauppsättningsinkluderingsfil måste du tänka på ordningen för indata och utdata. Mer information om ordningen för omformningar finns i [Konventioner för att skapa omformningar](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Skapa utökade dimensioner. Mer information om tillgängliga dimensionstyper finns i [Utökade Dimensioner](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. När du arbetar i datauppsättningsprofilen öppnar du [!DNL Profile Manager] och klickar på **[!UICONTROL Dataset]** för att visa den befintliga datauppsättningen med filer.

   * Om du vill visa [!DNL Log Processing Dataset Include]-filerna klickar du på **[!UICONTROL Log Processing]**.

   * Om du vill visa [!DNL Transformation Dataset Include]-filerna klickar du på **[!UICONTROL Transformation]**.

1. Skapa en ny [!DNL Log Processing]- eller [!DNL Transformation Dataset Include]-fil genom att utföra något av följande steg:

   * Klicka på **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]** i kolumnen [!DNL User] för katalogen Loggbearbetning. En fil med namnet [!DNL New Log Processing.cfg] visas i katalogen.

   * Klicka på **[!UICONTROL Create]** > **[!UICONTROL New Transformation]** i kolumnen [!DNL User] för katalogen Transformation. En fil med namnet [!DNL New Transformation.cfg] visas i katalogen.

1. Byt namn på den nya filen genom att högerklicka på bockmarkeringen i kolumnen [!DNL User] och skriva det nya namnet i parametern File.

   ![Steginformation](assets/vis_ProfileManager_RenameFile.png)

1. Högerklicka på bockmarkeringen för den namnändrade filen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Konfigurationsfönstret visas.
1. Redigera parametrarna i konfigurationsfilen efter behov. I [Loggbearbetningsdatauppsättningen innehåller filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) eller [Omvandlingsdatauppsättningen innehåller filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) finns beskrivningar av tillgängliga parametrar.
1. Om du vill spara ändringarna högerklickar du **[!UICONTROL (modified)]** högst upp i fönstret och klickar på **[!UICONTROL Save]**.
1. Om du vill att de lokalt gjorda ändringarna ska börja gälla högerklickar du i [!DNL Profile Manager] på bockmarkeringen för filen i kolumnen [!DNL User] och sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsinkluderingsfilen tillhör. Ombearbetning eller omformning av data börjar efter synkronisering av datauppsättningsprofilen.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

Mer information om hur du redigerar en datauppsättning med filer som du har skapat finns i [Redigera befintliga datauppsättningar med filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
