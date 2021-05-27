---
description: Geography-profilen som ingår i data workbenchGeography är en intern profil som ger ytterligare funktionalitet för ditt Adobe-program.
title: Installera geografisk profil
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Installerar geografisk profil{#installing-the-geography-profile}

Geography-profilen som ingår i data workbenchGeography är en intern profil som ger ytterligare funktionalitet för ditt Adobe-program.

Precis som med alla andra interna profiler från Adobe bör profilen [!DNL Geography] inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

Profilen [!DNL Geography] innehåller flera transformeringsdatauppsättningar med filer (som finns i mappen [!DNL Dataset\Transformation\Geography]) som definierar geografiska dimensioner. Nedan följer en lista över transformeringsdatauppsättningen som innehåller filer som ingår i profilen [!DNL Geography]:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Var och en av filerna namnges för den utökade dimension som definieras i den. Ytterligare en fil, [!DNL IPLookup.cfg], definierar flera geografiska datafält som används för att definiera dimensioner i den andra omformningsdatauppsättningen inklusive filer.

Mer information om att inkludera filer i omformningsdatauppsättningar finns i *Konfigurationshandboken för datauppsättningar*.

**Installera  [!DNL Geography] profilen på data workbench-servern**

>[!NOTE]
>
>Följande installationsanvisningar förutsätter att du har installerat data workbench och upprättat en anslutning mellan data workbench och den data workbench-server där du installerar data workbench [!DNL Geography]. Om du inte har gjort det läser du *Datans Workbench användarhandbok*.

1. Öppna mappen Profiler från filen [!DNL .zip] som du har fått från Adobe.
1. Kopiera mappen [!DNL Geography] till mappen Profiles i installationskatalogen för data workbench-servern. Du vill avsluta med en [!DNL ...\Profiles\Geography]-mapp på din data workbench-server, vilket visas i följande exempel. Namnen på de andra mapparna i mappen Profiler kan skilja sig från de som visas.

   ![Steginformation](assets/Geo_installProfiles_dir.png)

1. Följ de här stegen för att uppdatera [!DNL profile.cfg]-filen för varje profil som du vill använda data workbench [!DNL Geography] med.

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Fönstret [!DNL profile.cfg] visas.

   1. I fönstret [!DNL profile.cfg] högerklickar du på **[!UICONTROL Directories]** och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Om du vill lägga till den nya katalogen i slutet av kataloglistan högerklickar du på numret eller namnet på den sista katalogen i listan och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Ange namnet på den nya katalogen: [!DNL Geography].
   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager] högerklickar du på bockmarkeringen för [!DNL profile.cfg] i kolumnen [!DNL User] och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe (inklusive profilen [!DNL Geography]), eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.
