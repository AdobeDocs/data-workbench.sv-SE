---
description: Under ombearbetningen rekonstruerar data workbench-servern datauppsättningen som du har angett i loggbehandlings- och transformeringsdatauppsättningskonfigurationsfilerna.
solution: Analytics
title: Förstå ombearbetning och omformning
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Förstå ombearbetning och omformning{#understanding-reprocessing-and-retransformation}

Under ombearbetningen rekonstruerar data workbench-servern datauppsättningen som du har angett i loggbehandlings- och transformeringsdatauppsättningskonfigurationsfilerna.

För att göra det måste data workbench-servern (InsightServer64.exe) slutföra både loggbearbetningsfasen och transformeringsfasen för datauppsättningen. När loggbearbetningen är klar utlöses omformningen automatiskt, men omformningen kan också ske oberoende av loggbearbetningen.

Under loggbearbetningsfasen har användare av data workbench inte åtkomst till data i datauppsättningen. Under omvandlingsfasen har användare av data workbench tillgång till aktuella data, men data samplas i stället för att vara fullständiga. Dataanalys kan fortsätta under omformning, men frågor slutförs bara så fort som omformningen sker.

## Återbearbetning {#section-92f1e46bf1534b3dba39e9493190b8ab}

Varje gång du utför någon av följande uppgifter sker loggbearbetning och därmed omvandling automatiskt för att rekonstruera datauppsättningen som du har angett i datauppsättningens konfigurationsfiler:

* Lägg till en ny datakälla.
* Lägg till en ny data workbench-server i klustret i [!DNL Profile.cfg] filen.
* Ändra [!DNL Cluster.cfg] filen.
* Ändra [!DNL Log Processing.cfg] filen eller en [!DNL Log Processing Dataset Include] fil, inklusive men inte begränsat till följande:

   * Lägg till en ny parameter
   * Ändra en omformning
   * Ändra parametrarna för starttid och sluttid

* Uppgradera din [!DNL Insight Server.exe] fil.

Du kan också starta ombearbetningen när som helst genom att ange ett tecken eller en kombination av tecken i parametern för ombearbetning i [!DNL Log Processing.cfg] filen och spara filen.

>[!NOTE]
>
>För att ombearbetningen ska ske måste parametern Pause i [!DNL Log Processing Mode.cfg] filen anges till false. Parameterns standardvärde är false, så det kanske inte krävs någon ändring av parametern. Mer information om [!DNL Log Processing Mode.cfg]finns i [Ytterligare konfigurationsfiler](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Omformning {#section-02446744549940ada8eba0573ec5575f}

Varje gång du ändrar någon information i [!DNL Transformation.cfg] filen eller i en [!DNL Transformation Dataset Include] fil, till exempel ändrar en omformning eller definierar en ny dimension, sker omformningen automatiskt.

Varje gång du ändrar uppslagsfiler som refereras i [!DNL Transformation.cfg] filen eller i en [!DNL Transformation Dataset Include] fil (inklusive uppslagsfiler för [!DNL Categorize], [!DNL FlatFileLookup]och [!DNL ODBCLookup] omformningar) måste du initiera omformningen genom att ange ett tecken eller en kombination av tecken i [!DNL Transformation.cfg] filens ombearbetningsparameter och spara filen.