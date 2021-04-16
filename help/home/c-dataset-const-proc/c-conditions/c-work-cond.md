---
description: Information om hur du lägger till, tar bort eller kopierar ett villkor.
title: Arbeta med villkor
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---

# Arbeta med villkor{#working-with-conditions}

Information om hur du lägger till, tar bort eller kopierar ett villkor.

* [Lägga till ett villkor i en datauppsättningskonfigurationsfil](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Ta bort ett villkor från en datauppsättningskonfigurationsfil](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Kopiera ett villkor](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Lägga till ett villkor i en datauppsättningskonfigurationsfil {#section-3e2a34db047b462585502f69722f6511}

1. När du arbetar i datauppsättningsprofilen använder du [!DNL Profile Manager] för att öppna den datauppsättningskonfigurationsfil som du vill redigera.

   * Mer information om hur du öppnar filen [!DNL Log Processing.cfg] finns i [Redigera konfigurationsfilen för loggbearbetning](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Mer information om hur du öppnar filen [!DNL Transformation.cfg] finns i [Redigera konfigurationsfilen för omvandling](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * Mer information om hur du öppnar en [!DNL Dataset Include]-fil finns i [Inkludera filer i datauppsättning](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. I datauppsättningens konfigurationsfil letar du reda på parametern Loggpost eller Villkor som du vill definiera.
1. Högerklicka på parametern och klicka på **[!UICONTROL Add new]**. Välj någon av följande villkorstyper:

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Redigera parametrarna för villkoret efter behov. Beskrivningar av parametrarna för varje villkor finns i relevanta avsnitt i denna bilaga.
1. Om du vill spara ändringarna högerklickar du **[!UICONTROL (modified)]** högst upp i fönstret och klickar på **[!UICONTROL Save]**.

1. Om du vill att de lokalt gjorda ändringarna ska börja gälla högerklickar du på bockmarkeringen för filen i kolumnen [!DNL User] och sedan på **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som filen tillhör.[!DNL Profile Manager,]

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

## Ta bort ett villkor från en datauppsättningskonfigurationsfil {#section-677270f93f1648c3a268ca2aea7d4540}

1. Högerklicka på namnet på villkoret eller numret som motsvarar villkoret som du vill ta bort.
1. Klicka på **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, där tal är numret som motsvarar villkoret som du vill ta bort.

## Så här kopierar du ett villkor {#section-00617bcf2c274f428686b2ec7f2d1db8}

Du kan kopiera ett villkor från en plats till en annan i samma fil, eller kopiera ett villkor från en datauppsättningskonfigurationsfil till en annan.

1. Högerklicka på namnet på villkoret eller numret som motsvarar villkoret som du vill kopiera och klicka på **[!UICONTROL Copy]**.
1. Högerklicka på namnet eller numret på det villkor under vilket du vill placera det kopierade villkoret och klicka sedan på **[!UICONTROL Paste]**.
