---
description: Steg för att skapa en ny inkluderingsfil för datauppsättningen.
title: Skapar en ny datauppsättning med inkluderade filer
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# Skapar en ny datauppsättning med inkluderade filer{#creating-new-dataset-include-files}

{{eol}}

Steg för att skapa en ny inkluderingsfil för datauppsättningen.

Du bör skapa en ny datauppsättningsinkluderingsfil för att kunna utföra följande konfigurationsåtgärder för datauppsättningar:

* Ange nya fält med data som ska skickas från loggbearbetning till omvandling.
* Definiera omformningar som gör något av följande:

   * Uppdatera befintliga loggfält.
   * Skapa nya fält som ska skickas från loggbearbetning till omvandling eller som används för att definiera utökade dimensioner.

      Mer information om tillgängliga omformningstyper finns i [Dataomvandlingar](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

      >[!NOTE]
      >
      >Om du definierar omformningar i en ny datauppsättningsinkluderingsfil måste du tänka på ordningen för indata och utdata. Mer information om omformningsordningen finns i [Konventioner för att konstruera omformningar](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6).

* Skapa utökade dimensioner. Mer information om tillgängliga dimensionstyper finns i [Utökade Dimensioner](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

1. Öppna dialogrutan [!DNL Profile Manager] och klicka **[!UICONTROL Dataset]** om du vill visa den befintliga datauppsättningen med filer.

   * Så här visar du [!DNL Log Processing Dataset Include] filer, klicka **[!UICONTROL Log Processing]**.

   * Så här visar du [!DNL Transformation Dataset Include] filer, klicka **[!UICONTROL Transformation]**.

1. Skapa ett nytt [!DNL Log Processing] eller [!DNL Transformation Dataset Include] filer genom att utföra något av följande steg:

   * I [!DNL User] kolumn för katalogen Loggbearbetning klickar du på **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**. En fil med namnet [!DNL New Log Processing.cfg] visas i katalogen.

   * I [!DNL User] -kolumn för Transformation-katalogen klickar du på **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**. En fil med namnet [!DNL New Transformation.cfg] visas i katalogen.

1. Byt namn på den nya filen genom att högerklicka på bockmarkeringen i dialogrutan [!DNL User] och skriva det nya namnet i parametern File.

   ![Steginformation](assets/vis_ProfileManager_RenameFile.png)

1. Högerklicka på bockmarkeringen för den namnändrade filen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Konfigurationsfönstret visas.
1. Redigera parametrarna i konfigurationsfilen efter behov. Se [Loggbehandlings-datauppsättningen innehåller filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) eller [Omvandlingsdatauppsättningen innehåller filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) för beskrivningar av tillgängliga parametrar.
1. Om du vill spara ändringarna högerklickar du **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör. Ombearbetning eller omformning av data börjar efter synkronisering av datauppsättningsprofilen.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

Information om hur du redigerar en datauppsättning med filer som du har skapat finns i [Redigera befintlig datauppsättning Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).
