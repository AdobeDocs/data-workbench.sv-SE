---
description: Steg för att redigera befintliga datauppsättningar är bland annat filer.
title: Redigera befintlig datauppsättning Inkludera filer
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# Redigera befintlig datauppsättning Inkludera filer{#editing-existing-dataset-include-files}

{{eol}}

Steg för att redigera befintliga datauppsättningar är bland annat filer.

Du öppnar en befintlig datauppsättningsinkluderingsfil med [!DNL Profile Manager] i data workbench.

Mer information om hur du öppnar och arbetar med [!DNL Profile Manager], se *Användarhandbok för Data Workbench*.

1. Öppna dialogrutan [!DNL Profile Manager] och klicka **[!UICONTROL Dataset]** för att visa innehållet i katalogen.

   * Öppna en [!DNL Log Processing Dataset Include] fil, klicka **[!UICONTROL Log Processing]** för att visa innehållet i katalogen.

   * Öppna en [!DNL Transformation Dataset Include] fil, klicka **[!UICONTROL Transformation]** för att visa innehållet i katalogen.

1. Högerklicka på bockmarkeringen bredvid den önskade datauppsättningsfilen och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Konfigurationsfönstret visas.

   Du kan även öppna en datauppsättningsinkluderingsfil från en [!DNL Transformation Dependency Maps]. Mer information om [!DNL Transformation Dependency Maps], se [Ombearbetning och omformning](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Redigera parametrarna i konfigurationsfilen efter behov. Se [Loggbehandlings-datauppsättningen innehåller filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) eller [Omvandlingsdatauppsättningen innehåller filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) för beskrivningar av parametrarna.

   När du redigerar en datauppsättning som innehåller en fil i ett arbetsbänksfönster för data kan du använda kortkommandon för grundläggande redigeringsfunktioner, som att klippa ut (Ctrl+x ), kopiera (Ctrl+C), klistra in (Ctrl+V), ångra (Ctrl+z ), göra om (Ctrl+Skift+z), markera avsnitt (klicka+dra) och markera alla (Ctrl+a). Du kan dessutom använda kortkommandona för att kopiera och klistra in text från en konfigurationsfil ( [!DNL .cfg]) till en annan.

1. Om du vill spara ändringarna högerklickar du **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör. Ombearbetning eller omformning av data börjar efter synkronisering av datauppsättningsprofilen.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.
