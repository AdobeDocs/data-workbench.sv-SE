---
description: Viktig information att tänka på när du redigerar filen Transformation.cfg.
title: Överväganden för transformeringskonfigurationsfilen
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Överväganden för transformeringskonfigurationsfilen{#considerations-for-the-transformation-configuration-file}

{{eol}}

Viktig information att tänka på när du redigerar filen Transformation.cfg.

* Om du ändrar någon av parametrarna i den här filen måste data omformas.
* Om du bearbetar om data kan du kontrollera [!DNL Transformation Progress] parameter i data workbench&#39;s [!DNL Processing Legend].

   Om du vill ha information om hur du bearbetar dina data eller [!DNL Processing Legend,] se [Ombearbetning och omformning](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]och [!DNL AppendURI] omformningar fungerar bara när de definieras i en [!DNL Transformation Dataset Configuration] -fil. Mer information om dessa omformningar finns i [Dataomvandlingar](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe rekommenderar att du definierar omformningar för omformningsfasen för datauppsättningskonstruktionen i en eller flera [!DNL Transformation Dataset Include] filer. Mer information finns i [Omvandlingsdatauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* Du kan lägga till någon av parametrarna som beskrivs ovan i [!DNL Transformation.cfg] genom att öppna och redigera filen i Anteckningar. Alla ändringar du gör och sparar visas när du öppnar filen på nytt i data workbench. När du lägger till en ny parameter använder du blankstegstangenten (inte tabbtangenten) för att dra in två (2) blanksteg till höger om föregående rubriknivå.

   Alla fel som inträffar under omformningsfasen av datauppsättningens konstruktionsprocess för en datauppsättningsprofil visas i [!DNL Profiles] nod på [!DNL Detailed Status] gränssnitt i data workbench. Mer information om [!DNL Detailed Status] -gränssnittet finns i *Användarhandbok för Data Workbench*.
