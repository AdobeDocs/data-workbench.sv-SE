---
description: Steg för att skapa en ny inkluderingsfil för datauppsättningen.
solution: Analytics
title: Skapar en ny datauppsättning med inkluderade filer
topic: Data workbench
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Skapar en ny datauppsättning med inkluderade filer{#creating-new-dataset-include-files}

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

* Skapa utökade dimensioner. Mer information om tillgängliga dimensionstyper finns i [Utökade dimensioner](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. När du arbetar i datauppsättningsprofilen öppnar du filen [!DNL Profile Manager] och klickar **[!UICONTROL Dataset]** för att visa de befintliga datauppsättningsinkluderingsfilerna.

   * Om du vill visa [!DNL Log Processing Dataset Include] filerna klickar du på **[!UICONTROL Log Processing]**.

   * Om du vill visa [!DNL Transformation Dataset Include] filerna klickar du på **[!UICONTROL Transformation]**.

1. Skapa en ny [!DNL Log Processing] eller [!DNL Transformation Dataset Include] nya filer genom att utföra något av följande steg:

   * Klicka på [!DNL User] > i kolumnen **[!UICONTROL Create]** för katalogen Loggbearbetning **[!UICONTROL New Log Processing]**. En fil med namnet [!DNL New Log Processing.cfg] visas i katalogen.

   * Klicka på [!DNL User] > i kolumnen **[!UICONTROL Create]** för omformningskatalogen **[!UICONTROL New Transformation]**. En fil med namnet [!DNL New Transformation.cfg] visas i katalogen.

1. Byt namn på den nya filen genom att högerklicka på bockmarkeringen i kolumnen och skriva det nya namnet i parametern Arkiv. [!DNL User]

   ![Steginformation](assets/vis_ProfileManager_RenameFile.png)

1. Högerklicka på bockmarkeringen för den namnändrade filen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Konfigurationsfönstret visas.
1. Redigera parametrarna i konfigurationsfilen efter behov. I [Loggbehandlings-datauppsättningen Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) eller [Omvandlingsdatauppsättningen Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) finns en beskrivning av de tillgängliga parametrarna.
1. Om du vill spara ändringarna högerklickar du **[!UICONTROL (modified)]** högst upp i fönstret och klickar på **[!UICONTROL Save]**.
1. Om du vill göra de lokalt gjorda ändringarna gällande [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör. Ombearbetning eller omformning av data börjar efter synkronisering av datauppsättningsprofilen.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profiler som tillhandahålls av Adobe, eftersom dina ändringar skrivs över när du installerar uppdateringar för dessa profiler.

Mer information om hur du redigerar en datauppsättning med filer som du har skapat finns i [Redigera befintliga datauppsättningar, inklusive filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
