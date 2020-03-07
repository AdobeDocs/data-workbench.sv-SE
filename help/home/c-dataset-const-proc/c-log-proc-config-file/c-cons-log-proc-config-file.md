---
description: Konceptuell information som ska beaktas när filen Log Processing.cfg redigeras.
solution: Analytics
title: Hänsyn till konfigurationsfilen för loggbearbetning
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Hänsyn till konfigurationsfilen för loggbearbetning{#considerations-for-the-log-processing-configuration-file}

Konceptuell information som ska beaktas när filen Log Processing.cfg redigeras.

* Datafiler bör inte flyttas mellan kataloger efter att källorna för en datauppsättning har definierats. De enda ytterligare filer som en katalog ska ta emot är nyskapade som är ett resultat av data workbench-servern som tar emot data från sensor(er).
* Om du ändrar någon av parametrarna i den här filen måste alla data bearbetas om. Parametern Pause i [!DNL Log Processing Mode.cfg] filen måste anges till false för att ombearbetningen ska ske. (Observera att den här parameterns standardvärde är false, så det kanske inte krävs någon ändring av parametern.) Mer information om [!DNL Log Processing Mode.cfg] filen finns i [Ytterligare konfigurationsfiler](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* Om du bearbetar om data kan du kontrollera parametern Loggbearbetningsförlopp i data workbenchs [!DNL Processing Legend].

   Mer information om hur du bearbetar data finns i [Återbearbetning och omformning](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). Se [Bearbeta förklaring](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* Filen kan [!DNL Log Processing.cfg] delas av flera datauppsättningsprofiler. Omformningar som definieras i [!DNL Log Processing.cfg] filen tillämpas på alla datauppsättningsprofiler som delar den här konfigurationsfilen.

   >[!NOTE]
   >
   >Adobe rekommenderar att du definierar omformningar för loggbearbetningen i en eller flera [!DNL dataset include] loggbearbetningsfiler. Mer information finns i [Loggbearbetning av datauppsättningen Inkludera filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* Du kan lägga till alla parametrar som beskrivs ovan till [!DNL Log Processing.cfg] filen genom att öppna och redigera filen i Anteckningar. Alla ändringar du gör och sparar visas när du öppnar filen på nytt i data workbench. När du lägger till en ny parameter använder du blankstegstangenten (inte tabbtangenten) för att dra in två (2) blanksteg till höger om föregående rubriknivå.

   Alla fel som inträffar under loggbearbetningsfasen i datauppsättningsprocessen för en datauppsättningsprofil visas i noden [!DNL Profiles] i [!DNL Detailed Status] gränssnittet i data workbench. Mer information om [!DNL Detailed Status] gränssnittet finns i *användarhandboken* för Data Workbench.
