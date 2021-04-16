---
description: Steg för att definiera utökade dimensioner.
title: Definiera utökade Dimensioner
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Definiera utökade Dimensioner{#defining-extended-dimensions}

Steg för att definiera utökade dimensioner.

1. När du arbetar i datauppsättningsprofilen öppnar du [!DNL Profile Manager] och klickar på **[!UICONTROL Dataset]** för att visa innehållet.
1. Öppna filen [!DNL Transformation.cfg] eller [!DNL Transformation Dataset Include]-filen som du vill definiera den utökade dimensionen i.

   * (Rekommenderas) Mer information om hur du öppnar en inkluderingsfil för datauppsättningar finns i [Inkludera datauppsättningar](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobe rekommenderar att du definierar utökade dimensioner i en eller flera nya [!DNL Transformation Dataset Include]-filer. Mer information finns i [Skapa ny datauppsättning Inkludera filer](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e).

   * Mer information om hur du öppnar filen [!DNL Transformation.cfg] finns i [Redigera konfigurationsfilen för omvandling](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Högerklicka på **[!UICONTROL Transformations]** och klicka på **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*.
1. Ange lämplig information för den utökade dimensionen. Beskrivningar av omformningstyperna och information om deras parametrar finns i följande avsnitt:

   * [Räkningsbara Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [Enkla Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [Många-till-många-Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [Numeriska Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      För alla utökade dimensioner som du definierar kan du lägga till en eller flera kommentarsrader i kommentarsparametern för att ytterligare beskriva dimensionen eller lägga till anteckningar om dess användning. Om du vill lägga till en kommentar högerklickar du på etiketten **[!UICONTROL Comments]** och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**.

1. När du har definierat de utökade dimensionerna i konfigurationsfilen sparar du filen lokalt och sparar den i datauppsättningsprofilen på data workbench-servern.
