---
description: Transformeringsfunktionen körs på en Insight Server FSU-dator för att möjliggöra export av loggkälldata för användning i andra program.
solution: Insight
title: Konfigurera Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Konfigurera Transform{#configuring-transform}

Transformeringsfunktionen körs på en Insight Server FSU-dator för att möjliggöra export av loggkälldata för användning i andra program.

[!DNL Transform] kan läsa [!DNL .vsl] filer, loggfiler, XML-filer och ODBC-data och exportera data som [!DNL .vsl] filer, textfiler eller avgränsade textfiler som kan användas av datalagerinläsningsrutiner, revisionsbyråer eller andra mål. Dataextraheringen och dataomvandlingen kan utföras kontinuerligt eller schemalagt. Varje [!DNL Insight Server] FSU som tillhandahåller utdata för ändrade händelsedata måste köras [!DNL Transform].

>[!NOTE]
>
>Vanligtvis [!DNL Transform] installeras på en [!DNL Insight Server] FSU. Implementeringen kan dock kräva installation på en [!DNL Insight Server] DPU. Kontakta Adobe om du vill ha mer information.

Mer information om systemkraven för installation, konfiguration och drift [!DNL Transform]finns i *dokumentet Minimum System Requirements* .

Adobe distribuerar [!DNL Transform] funktionen som en profil i [!DNL .zip] filen för [!DNL Insight Server] versionspaketet. Profilen [!DNL Transform] är en intern profil som innehåller ytterligare funktioner för [!DNL Insight Server]. Precis som med alla andra interna profiler från Adobe bör profilen inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

Profilen består av följande filer:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* en loggbearbetningsdatauppsättning innehåller fil

Alla dessa filer finns i profilens [!DNL Dataset] mapp.

**Installera[!DNL Transform]profilen på[!DNL Insight Server]**

>[!NOTE]
>
>I följande installationsanvisningar förutsätts att du har installerat [!DNL Insight] och upprättat en anslutning mellan [!DNL Insight] och den [!DNL Insight Server] som du installerar [!DNL Transform]. Om du inte har gjort det läser du * [!DNL Insight] Användarhandbok*.

1. Öppna [!DNL .zip] filen för [!DNL Insight Server] versionspaketet och öppna [!DNL Profiles] mappen i den [!DNL .zip] filen.
1. Kopiera [!DNL Transform] mappen till [!DNL Profiles] mappen i din [!DNL Insight Server] installationskatalog. Du vill avsluta med en [!DNL ...\Profiles\Transform] mapp på din dator [!DNL Insight Server] enligt följande exempel.

   ![Steginformation](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Om du har följt alla steg för installationen [!DNL Insight Server] (se [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)) kan det hända att du redan har en [!DNL Transform] mapp i katalogen Profiles.

1. Följ de här stegen för att uppdatera [!DNL profile.cfg] filen för profilen som du vill använda [!DNL Transform]. Datauppsättningen bearbetas om när de här stegen har slutförts.

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret [!DNL profile.cfg] visas.

   1. Högerklicka i [!DNL profile.cfg]fönstret **[!UICONTROL Directories]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Om du vill lägga till den nya katalogen i slutet av kataloglistan högerklickar du på numret eller namnet på den sista katalogen i listan och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Ange namnet på den nya katalogen: [!DNL Transform]
   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen för [!DNL profile.cfg] i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Spara inte den ändrade konfigurationsfilen i någon av de interna profiler som tillhandahålls av Adobe (inklusive profilen), eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

