---
description: De nya dimensionerna som du skapar med Data Workbench (kallas härledda dimensioner) är klientsidans dimensioner.
title: Arbeta med härledda dimensioner
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---

# Arbeta med härledda dimensioner{#work-with-derived-dimensions}

{{eol}}

De nya dimensionerna som du skapar med Data Workbench (kallas härledda dimensioner) är klientsidans dimensioner.

Istället för att definiera de här dimensionerna under datauppsättnings- och uppdateringsprocessen (i [!DNL Transformation.cfg] fil) på Datans Workbench serverdatorer skapas och lagras härledda dimensioner var för sig som [!DNL .dim] filer i en profil. Det innebär att du kan ändra befintliga och skapa nya härledda dimensioner utan att bearbeta om datauppsättningen.

>[!NOTE]
>
>Mer information om dimensioner än vad som anges i det här avsnittet finns i programguiden för Data Workbench.

Mer information om datauppsättningens konfiguration och uppdateringsprocess finns i *Konfigurationshandbok för datauppsättning*.

## Skapa en härledd dimension {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Om du vill skapa en härledd dimension kan du antingen kopiera och ändra en befintlig dimension eller spara en dimension från en visualisering.

## Skapa härledda dimensioner från en befintlig dimension {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Användare vill oftast skapa nya tidsdimensioner av befintliga. Du kan till exempel skapa en ny dimension,&quot;De senaste fem dagarna&quot;, från den befintliga dimensionen&quot;De senaste sju dagarna&quot;.

1. I [!DNL Profile Manager], i *profilnamn* högerklicka på bockmarkeringen för en dimension som liknar den dimension som du vill skapa och klicka sedan på **[!UICONTROL Copy]**.

   Om du till exempel vill kopiera [!DNL Last 7 Days.dim] från mappen Reporting i [!DNL Traffic] högerklickar du på bockmarkeringen för filnamnet i dialogrutan [!DNL Traffic] kolumn och klicka **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Högerklicka i dialogrutan [!DNL User] -kolumn för mappen där du vill lagra den kopierade dimensionen och klicka på **[!UICONTROL Paste]**.

   Dimensionen visas i den markerade Dimensionen med en bockmarkering i [!DNL User] kolumn.

1. Om du vill byta namn på den nya dimensionen högerklickar du på dess bockmarkering i dialogrutan [!DNL User] kolumn och skriv det nya namnet i [!DNL File] fält.
1. I högerklicksmenyn klickar du på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Dimensionens definitionsparametrar visas.
1. Ändra parametrarna efter behov för att definiera den nya dimensionen.

   För tidsdimensioner behöver du troligen bara ändra parametrarna Antal och Intervall.

1. Om du vill spara filen högerklickar du **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   Om du vill att alla användare av en profil ska använda den dimension som du har skapat måste du överföra den till profilen med hjälp av [!DNL Profile Manager]. Mer information finns i [Publicera filer i din arbetsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Du kan nu använda den nya dimensionen i hela den aktuella profilen genom att markera den på samma sätt som andra inbyggda dimensioner.

## Spara en dimension från en visualisering {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Du kan spara utökade dimensioner från processkartor och segment. Anvisningar om hur du sparar en dimension från en processkarta finns i [Spara Dimensioner från processkartor](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Anvisningar om hur du sparar en segmentdimension finns i [Skapa Dimensioner för segment](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) på sidan 82.

## Spara ett segment som en dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Du kan också spara definierade segment som en dimension. Om du vill se steg går du till [Återanvända segmentvisualisering](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Redigera en befintlig härledd dimension {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   n [!DNL Profile Manager], i *profilnamn* högerklicka på bockmarkeringen för den dimensionsfil som du vill redigera och klicka på **[!UICONTROL Make Local]**.
1. Högerklicka på bockmarkeringen för dimensionsfilen i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Slutför parametrarna efter behov. Mer information får du av Adobe Consulting Services.
1. Om du vill spara filen högerklickar du **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   Om du vill att alla användare av en profil ska använda den ändrade dimensionen måste du överföra den till profilen med hjälp av [!DNL Profile Manager]. Mer information finns i [Publicera filer i din arbetsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
