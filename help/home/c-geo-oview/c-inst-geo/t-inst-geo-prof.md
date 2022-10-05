---
description: Geography-profilen som ingår i data workbenchGeography är en intern profil som ger ytterligare funktionalitet för ditt Adobe-program.
title: Installera geografisk profil
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Installera geografisk profil{#installing-the-geography-profile}

{{eol}}

Geography-profilen som ingår i data workbenchGeography är en intern profil som ger ytterligare funktionalitet för ditt Adobe-program.

Precis som med alla andra interna profiler från Adobe, [!DNL Geography] bör inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

The [!DNL Geography] profilen innehåller flera transformeringsdatauppsättningar med filer (finns i [!DNL Dataset\Transformation\Geography] mapp) som definierar geografiska dimensioner. Nedan följer en lista över transformeringsdatauppsättningen som innehåller filer som finns i [!DNL Geography] profil:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Var och en av filerna namnges för den utökade dimension som definieras i den. Ytterligare en fil, [!DNL IPLookup.cfg]definierar flera geografiska datafält som används för att definiera dimensioner i den andra omformningsdatauppsättningen inklusive filer.

Mer information om att inkludera filer i omformningsdatauppsättningen finns i *Konfigurationshandbok för datauppsättning*.

**Så här installerar du [!DNL Geography] profil på data workbench-servern**

>[!NOTE]
>
>Följande installationsanvisningar förutsätter att du har installerat data workbench och upprättat en anslutning mellan data workbench och den data workbench-server där du installerar data workbench [!DNL Geography]. Om du inte har gjort det kan du läsa *Användarhandbok för Data Workbench*.

1. Öppna mappen Profiler från [!DNL .zip] som du har fått från Adobe.
1. Kopiera [!DNL Geography] till mappen Profiles i installationskatalogen för data workbench-servern. Du vill avsluta med en [!DNL ...\Profiles\Geography] på din data workbench-server, vilket visas i följande exempel. Namnen på de andra mapparna i mappen Profiler kan skilja sig från de som visas.

   ![Steginformation](assets/Geo_installProfiles_dir.png)

1. Använd följande steg för att uppdatera [!DNL profile.cfg] fil för varje profil som du vill använda data workbench med [!DNL Geography].

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL profile.cfg] visas.

   1. I [!DNL profile.cfg] fönster, högerklicka **[!UICONTROL Directories]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Om du vill lägga till den nya katalogen i slutet av kataloglistan högerklickar du på numret eller namnet på den sista katalogen i listan och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Ange namnet på den nya katalogen: [!DNL Geography].
   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager], högerklicka på bockmarkeringen för [!DNL profile.cfg] i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe (inklusive [!DNL Geography] profil) när ändringarna skrivs över när du installerar uppdateringar för dessa profiler.
