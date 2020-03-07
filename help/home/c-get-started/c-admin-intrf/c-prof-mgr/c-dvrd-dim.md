---
description: De nya dimensionerna som du skapar med Data Workbench (kallas härledda dimensioner) är mått på klientsidan.
solution: Analytics
title: Arbeta med härledda dimensioner
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arbeta med härledda dimensioner{#work-with-derived-dimensions}

De nya dimensionerna som du skapar med Data Workbench (kallas härledda dimensioner) är mått på klientsidan.

I stället för att definiera de här dimensionerna under datauppsättnings- och uppdateringsprocessen (i [!DNL Transformation.cfg] filen) på Data Workbench-serverdatorerna, skapas och lagras härledda dimensioner individuellt som [!DNL .dim] filer i en profil. Det innebär att du kan ändra befintliga och skapa nya härledda dimensioner utan att bearbeta om datauppsättningen.

>[!NOTE]
>
>Mer information om dimensioner än vad som anges i det här avsnittet finns i lämplig programguide för Data Workbench.

Mer information om datauppsättningens konfiguration och uppdateringsprocess finns i konfigurationsguiden för *datauppsättningar*.

## Skapa en härledd dimension {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Om du vill skapa en härledd dimension kan du antingen kopiera och ändra en befintlig dimension eller spara en dimension från en visualisering.

## Skapa härledda dimensioner från en befintlig dimension {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Användare vill oftast skapa nya tidsdimensioner av befintliga. Du kan till exempel skapa en ny dimension,&quot;De senaste fem dagarna&quot;, från den befintliga dimensionen&quot;De senaste sju dagarna&quot;.

1. I [!DNL Profile Manager]kolumnen *Profilnamn* högerklickar du på bockmarkeringen för en dimension som liknar den dimension som du vill skapa och klickar sedan på **[!UICONTROL Copy]**.

   Om du till exempel vill kopiera filen [!DNL Last 7 Days.dim] från mappen Rapportering i [!DNL Traffic] profilen högerklickar du på bockmarkeringen för filnamnet i [!DNL Traffic] kolumnen och klickar på **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Högerklicka i [!DNL User] kolumnen för mappen där du vill spara den kopierade dimensionen och klicka sedan på **[!UICONTROL Paste]**.

   Dimensionen visas i den valda Dimensions-mappen med en bock i [!DNL User] kolumnen.

1. Om du vill byta namn på den nya dimensionen högerklickar du på bockmarkeringen i kolumnen och skriver det nya namnet i [!DNL User] [!DNL File] fältet.
1. Högerklicka på menyn och klicka **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Dimensionens definitionsparametrar visas.
1. Ändra parametrarna efter behov för att definiera den nya dimensionen.

   För tidsdimensioner behöver du troligen bara ändra parametrarna Antal och Intervall.

1. Om du vill spara filen högerklickar du **[!UICONTROL (modified)]** längst upp i fönstret och klickar på **[!UICONTROL Save]**.

   Om du vill att alla användare av en profil ska använda den dimension som du har skapat måste du överföra den till profilen med hjälp av [!DNL Profile Manager]. Mer information finns i [Publicera filer till din arbetsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Du kan nu använda den nya dimensionen i hela den aktuella profilen genom att markera den på samma sätt som andra inbyggda dimensioner.

## Spara en dimension från en visualisering {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Du kan spara utökade dimensioner från processkartor och segment. Anvisningar om hur du sparar en dimension från en processkarta finns i [Spara dimensioner från processkartor](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Anvisningar om hur du sparar en segmentdimension finns i [Skapa segmentdimensioner](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) på sidan 82.

## Spara ett segment som en dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Du kan också spara definierade segment som en dimension. Stegen finns i [Återanvända segmentvisualisering](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Redigera en befintlig härledd dimension {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   I [!DNL Profile Manager]kolumnen *profilnamn* högerklickar du på bockmarkeringen för den dimensionsfil som du vill redigera och klickar på **[!UICONTROL Make Local]**.
1. Högerklicka på bockmarkeringen för dimensionsfilen i [!DNL User] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Slutför parametrarna efter behov. Mer information får du av Adobes konsulttjänster.
1. Om du vill spara filen högerklickar du **[!UICONTROL (modified)]** längst upp i fönstret och klickar på **[!UICONTROL Save]**.

   Om du vill att alla användare av en profil ska använda den ändrade dimensionen måste du överföra den till profilen med hjälp av [!DNL Profile Manager]. Mer information finns i [Publicera filer till din arbetsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

