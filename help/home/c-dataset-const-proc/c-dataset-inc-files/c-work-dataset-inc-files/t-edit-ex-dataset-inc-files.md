---
description: Steg för att redigera befintliga datauppsättningar är bland annat filer.
solution: Analytics
title: Redigera befintlig datauppsättning Inkludera filer
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Redigera befintlig datauppsättning Inkludera filer{#editing-existing-dataset-include-files}

Steg för att redigera befintliga datauppsättningar är bland annat filer.

Du öppnar en befintlig datauppsättningsinkluderingsfil med hjälp av [!DNL Profile Manager] i data workbench.

Mer information om hur du öppnar och arbetar med [!DNL Profile Manager]filen finns i *användarhandboken* för Data Workbench.

1. När du arbetar i datauppsättningsprofilen öppnar du [!DNL Profile Manager] och klickar på **[!UICONTROL Dataset]** för att visa innehållet i katalogen.

   * Om du vill öppna en [!DNL Log Processing Dataset Include] fil klickar du **[!UICONTROL Log Processing]** för att visa innehållet i katalogen.

   * Om du vill öppna en [!DNL Transformation Dataset Include] fil klickar du **[!UICONTROL Transformation]** för att visa innehållet i katalogen.

1. Högerklicka på bockmarkeringen bredvid den önskade datauppsättningsfilen och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Konfigurationsfönstret visas.

   Du kan också öppna en datauppsättningsinkluderingsfil från en [!DNL Transformation Dependency Maps]. Mer information om [!DNL Transformation Dependency Maps]finns i [Återbearbetning och omformning](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Redigera parametrarna i konfigurationsfilen efter behov. Mer information om parametrarna finns i [Loggbehandling av datauppsättning Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) eller [Omvandlingsdatauppsättning Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) .

   När du redigerar en datauppsättning som innehåller en fil i ett arbetsbänksfönster för data kan du använda kortkommandon för grundläggande redigeringsfunktioner, som att klippa ut (Ctrl+x ), kopiera (Ctrl+C), klistra in (Ctrl+V), ångra (Ctrl+z ), göra om (Ctrl+Skift+z), markera avsnitt (klicka+dra) och markera alla (Ctrl+a). Du kan dessutom använda kortkommandona för att kopiera och klistra in text från en konfigurationsfil ( [!DNL .cfg]) till en annan.

1. Om du vill spara ändringarna högerklickar du **[!UICONTROL (modified)]** högst upp i fönstret och klickar på **[!UICONTROL Save]**.
1. Om du vill göra de lokalt gjorda ändringarna gällande [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör. Ombearbetning eller omformning av data börjar efter synkronisering av datauppsättningsprofilen.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profiler som tillhandahålls av Adobe, eftersom dina ändringar skrivs över när du installerar uppdateringar för dessa profiler.

