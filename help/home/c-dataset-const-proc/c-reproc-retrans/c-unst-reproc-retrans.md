---
description: Under ombearbetningen rekonstruerar data workbench-servern datauppsättningen som du har angett i loggbehandlings- och transformeringsdatauppsättningskonfigurationsfilerna.
title: Förstå ombearbetning och omformning
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# Förstå ombearbetning och omformning{#understanding-reprocessing-and-retransformation}

{{eol}}

Under ombearbetningen rekonstruerar data workbench-servern datauppsättningen som du har angett i loggbehandlings- och transformeringsdatauppsättningskonfigurationsfilerna.

För att göra det måste data workbench-servern (InsightServer64.exe) slutföra både loggbearbetningsfasen och transformeringsfasen för datauppsättningen. När loggbearbetningen är klar utlöses omformningen automatiskt, men omformningen kan också ske oberoende av loggbearbetningen.

Under loggbearbetningsfasen har användare av data workbench inte åtkomst till data i datauppsättningen. Under omvandlingsfasen har användare av data workbench tillgång till aktuella data, men data samplas i stället för att vara fullständiga. Dataanalys kan fortsätta under omformning, men frågor slutförs bara så fort som omformningen sker.

## Återbearbetning {#section-92f1e46bf1534b3dba39e9493190b8ab}

Varje gång du utför någon av följande uppgifter sker loggbearbetning och därmed omvandling automatiskt för att rekonstruera datauppsättningen som du har angett i datauppsättningens konfigurationsfiler:

* Lägg till en ny datakälla.
* Lägg till en ny data workbench-server till ditt kluster i [!DNL Profile.cfg] -fil.
* Ändra [!DNL Cluster.cfg] -fil.
* Ändra [!DNL Log Processing.cfg] eller en [!DNL Log Processing Dataset Include] fil, inklusive men inte begränsat till följande:

   * Lägg till en ny parameter
   * Ändra en omformning
   * Ändra parametrarna för starttid och sluttid

* Uppgradera din [!DNL Insight Server.exe] -fil.

Du kan också starta ombearbetningen när som helst genom att ange valfritt tecken eller valfri kombination av tecken i Reprocess-parametern i [!DNL Log Processing.cfg] och spara filen.

>[!NOTE]
>
>För att ombearbetningen ska ske finns parametern Pause i [!DNL Log Processing Mode.cfg] filen måste anges till false. Parameterns standardvärde är false, så det kanske inte krävs någon ändring av parametern. Mer information om [!DNL Log Processing Mode.cfg], se [Ytterligare konfigurationsfiler](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Omformning {#section-02446744549940ada8eba0573ec5575f}

Varje gång du ändrar någon information i dialogrutan [!DNL Transformation.cfg] eller i en [!DNL Transformation Dataset Include] -fil, som att ändra en omformning eller definiera en ny dimension, utförs omformningen automatiskt.

Varje gång du ändrar uppslagsfiler som refereras i [!DNL Transformation.cfg] eller i en [!DNL Transformation Dataset Include] fil (inklusive sökfiler för [!DNL Categorize], [!DNL FlatFileLookup]och [!DNL ODBCLookup] omformningar) måste du initiera omformningen genom att ange ett tecken eller en kombination av tecken i parametern Reprocess i [!DNL Transformation.cfg] och spara filen.
