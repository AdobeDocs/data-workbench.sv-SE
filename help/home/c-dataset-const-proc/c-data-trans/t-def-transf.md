---
description: Du kan definiera dataomformningar som ska användas under loggbearbetnings- eller omformningsfasen för datauppsättningens konstruktion.
title: Definiera en omformning
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Definiera en omformning{#defining-a-transformation}

{{eol}}

Du kan definiera dataomformningar som ska användas under loggbearbetnings- eller omformningsfasen för datauppsättningens konstruktion.

>[!NOTE]
>
>Adobe rekommenderar att du definierar omformningar i antingen [!DNL Log Processing] eller [!DNL Transformation Dataset Include] filer i stället för i [!DNL Log Processing.cfg] eller [!DNL Transformation.cfg].

Följande omformningar fungerar bara när de definieras i [!DNL Transformation.cfg] eller i en [!DNL Transformation Dataset Include] fil:

* [AppendURI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)I
* [Korsrader](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [Uppslagsrader](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [ODBC-datakällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Skändis](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**Definiera en omformning**

1. Använd [!DNL Profile Manager] för att öppna den datauppsättningskonfigurationsfil där du vill definiera omvandlingen.

   * (Rekommenderas) Om du vill öppna en inkluderingsfil för en datauppsättning går du till [Datauppsättningen innehåller filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).
   * Öppna [!DNL Log Processing.cfg] -fil, se [Redigera konfigurationsfilen för loggbearbetning](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Öppna [!DNL Transformation.cfg] -fil, se [Redigera transformeringskonfigurationsfilen](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Högerklicka **[!UICONTROL Transformations]** och sedan klicka **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*.
1. Ange lämplig information för omvandlingen. Beskrivningar av omformningstyperna och information om deras parametrar finns i följande avsnitt:

   * [Standardomformningar](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [URI-omformningar](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [Integrera uppslagsdata](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. När du har definierat dina omvandlingar i konfigurationsfilen sparar du filen lokalt och sparar den i datauppsättningsprofilen på data workbench-servern.

       Tips för att definiera och redigera omformningar:
   
   * När du redigerar konfigurationen för en omformning i ett datautbyte-fönster kan du använda kortkommandon för grundläggande redigeringsfunktioner, t.ex. Klipp ut (Ctrl+X), Kopiera (Ctrl+C), Klistra in (Ctrl+V), Ångra (Ctrl+Z), Gör om (Ctrl+Skift+Z), markera avsnitt (klicka+dra) och markera alla (Ctrl+a). Du kan dessutom använda kortkommandona för att kopiera och klistra in text eller hela omformningsdefinitioner från en konfigurationsfil ( [!DNL .cfg]) till en annan.
   * För alla omformningar som du definierar kan du lägga till en eller flera kommentarsrader i kommentarsparametern för att ytterligare beskriva omformningen eller lägga till anteckningar om hur den används. Om du vill lägga till en kommentar med data workbench högerklickar du på **[!UICONTROL Comments]** etikett och klicka sedan på **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

   * Du kan öppna konfigurationen för alla omformningar från en [!DNL Transformation Dependency Map]. När du har öppnat konfigurationen kan du redigera den och spara ändringarna. Mer information om [!DNL Transformation Dependency Maps], se [Verktyg för datauppsättningskonfiguration](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

   * En tom strängutmatning från en omformning kan skriva över en sträng som inte är tom i utdatafältet.
