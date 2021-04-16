---
description: Viktig information att tänka på när du redigerar filen Transformation.cfg.
title: Överväganden för transformeringskonfigurationsfilen
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Överväganden för transformeringskonfigurationsfilen{#considerations-for-the-transformation-configuration-file}

Viktig information att tänka på när du redigerar filen Transformation.cfg.

* Om du ändrar någon av parametrarna i den här filen måste data omformas.
* Om du bearbetar om data kan du kontrollera parametern [!DNL Transformation Progress] i [!DNL Processing Legend] för data workbench.

   Mer information om hur du ombearbetar data eller [!DNL Processing Legend,] finns i [Återbearbetning och omformning](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize]och  [!DNL AppendURI] omformningar fungerar bara när de definieras i en  [!DNL Transformation Dataset Configuration] fil. Mer information om dessa omformningar finns i [Datatransformeringar](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe rekommenderar att du definierar omformningar för omformningsfasen för datauppsättningens konstruktion i en eller flera [!DNL Transformation Dataset Include]-filer. Mer information finns i [Omvandlingsdatauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Du kan lägga till någon av parametrarna som beskrivs ovan i [!DNL Transformation.cfg]-filen genom att öppna och redigera filen i Anteckningar. Alla ändringar du gör och sparar visas när du öppnar filen på nytt i data workbench. När du lägger till en ny parameter använder du blankstegstangenten (inte tabbtangenten) för att dra in två (2) blanksteg till höger om föregående rubriknivå.

   Alla fel som inträffar under omformningsfasen av datauppsättningskonstruktionsprocessen för en datauppsättningsprofil visas i noden [!DNL Profiles] i gränssnittet [!DNL Detailed Status] i data workbench. Mer information om gränssnittet [!DNL Detailed Status] finns i *användarhandboken för Datan Workbench*.
