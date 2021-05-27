---
description: Transformeringsfunktionen körs på en Insight Server FSU-dator för att möjliggöra export av loggkälldata för användning i andra program.
title: Konfigurera Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Konfigurerar Transform{#configuring-transform}

Transformeringsfunktionen körs på en Insight Server FSU-dator för att möjliggöra export av loggkälldata för användning i andra program.

[!DNL Transform] kan läsa  [!DNL .vsl] filer, loggfiler, XML-filer och ODBC-data och exportera data som  [!DNL .vsl] filer, textfiler eller avgränsade textfiler som kan användas av inläsningsrutiner, revisionsbyråer eller andra mål för data warehouse. Dataextraheringen och dataomvandlingen kan utföras kontinuerligt eller schemalagt. Varje [!DNL Insight Server] FSU som tillhandahåller utdata för ändrade händelsedata måste köra [!DNL Transform].

>[!NOTE]
>
>Vanligtvis är [!DNL Transform] installerat på en [!DNL Insight Server] FSU. Implementeringen kan dock kräva installation på en [!DNL Insight Server] DPU. Kontakta Adobe om du vill ha mer information.

Mer information om systemkraven för installation, konfigurering och drift [!DNL Transform] finns i dokumentet *Minimum System Requirements*.

Adobe distribuerar [!DNL Transform]-funktionen som en profil i [!DNL .zip]-filen för [!DNL Insight Server]-versionspaketet. Profilen [!DNL Transform] är en intern profil som ger ytterligare funktioner för [!DNL Insight Server]. Precis som med alla andra interna profiler från Adobe bör profilen inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

Profilen består av följande filer:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* en loggbearbetningsdatauppsättning innehåller fil

Alla dessa filer finns i mappen [!DNL Dataset] för profilen.

**Installera  [!DNL Transform] profilen på[!DNL Insight Server]**

>[!NOTE]
>
>Följande installationsanvisningar förutsätter att du har installerat [!DNL Insight] och upprättat en anslutning mellan [!DNL Insight] och [!DNL Insight Server] som du installerar [!DNL Transform] på. Om du inte har gjort det läser du användarhandboken* för * [!DNL Insight].

1. Öppna [!DNL .zip]-filen för [!DNL Insight Server]-versionspaketet och öppna mappen [!DNL Profiles] i den [!DNL .zip]-filen.
1. Kopiera mappen [!DNL Transform] till mappen [!DNL Profiles] i installationskatalogen för [!DNL Insight Server]. Du vill avsluta med en [!DNL ...\Profiles\Transform]-mapp på din [!DNL Insight Server] enligt följande exempel.

   ![Steginformation](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Om du har följt alla steg för att installera [!DNL Insight Server] (se [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)) kan du redan ha en [!DNL Transform]-mapp i katalogen Profiles.

1. Följ de här stegen för att uppdatera [!DNL profile.cfg]-filen för profilen som du vill använda [!DNL Transform] med. Datauppsättningen bearbetas om när de här stegen har slutförts.

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret [!DNL profile.cfg] visas.

   1. Högerklicka på **[!UICONTROL Directories]** i [!DNL profile.cfg]fönstret och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Om du vill lägga till den nya katalogen i slutet av kataloglistan högerklickar du på numret eller namnet på den sista katalogen i listan och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Ange namnet på den nya katalogen: [!DNL Transform]
   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager] högerklickar du på bockmarkeringen för [!DNL profile.cfg] i kolumnen [!DNL User] och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe (inklusive profilen), eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.
