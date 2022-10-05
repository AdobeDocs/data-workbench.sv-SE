---
description: Transformeringsfunktionen körs på en Insight Server FSU-dator för att möjliggöra export av loggkälldata för användning i andra program.
title: Konfigurera Transform
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Konfigurera Transform{#configuring-transform}

{{eol}}

Transformeringsfunktionen körs på en Insight Server FSU-dator för att möjliggöra export av loggkälldata för användning i andra program.

[!DNL Transform] kan läsa [!DNL .vsl] filer, loggfiler, XML-filer och ODBC-data och exportera data som [!DNL .vsl] filer, textfiler eller avgränsade textfiler som kan användas av inläsningsrutiner, revisionsbyråer eller andra mål för data warehouse. Dataextraheringen och dataomvandlingen kan utföras kontinuerligt eller schemalagt. Varje [!DNL Insight Server] FSU som tillhandahåller utdata för ändrade händelsedata måste köras [!DNL Transform].

>[!NOTE]
>
>Vanligtvis [!DNL Transform] är installerat på en [!DNL Insight Server] FSU. Implementeringen kan dock kräva installation på en [!DNL Insight Server] DPU. Kontakta Adobe om du vill ha mer information.

Mer information om systemkraven för installation, konfiguration och drift [!DNL Transform], se *Lägsta systemkrav* -dokument.

Adobe distribuerar [!DNL Transform] som en profil i [!DNL .zip] filen för [!DNL Insight Server] versionspaket. The [!DNL Transform] profil är en intern profil som ger ytterligare funktioner för [!DNL Insight Server]. Precis som med alla andra interna profiler från Adobe bör profilen inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

Profilen består av följande filer:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* en loggbearbetningsdatauppsättning innehåller fil

Alla dessa filer finns i [!DNL Dataset] mapp för profilen.

**Så här installerar du [!DNL Transform] profil på[!DNL Insight Server]**

>[!NOTE]
>
>Följande installationsanvisningar förutsätter att du har installerat [!DNL Insight] och upprättade en koppling mellan [!DNL Insight] och [!DNL Insight Server] som du installerar [!DNL Transform]. Om du inte har gjort det, se * [!DNL Insight] Användarhandbok*.

1. Öppna [!DNL .zip] filen för [!DNL Insight Server] och öppna [!DNL Profiles] i den mappen [!DNL .zip] -fil.
1. Kopiera [!DNL Transform] mapp till [!DNL Profiles] i din [!DNL Insight Server] installationskatalog. Du vill avsluta med en [!DNL ...\Profiles\Transform] på din [!DNL Insight Server] som i följande exempel.

   ![Steginformation](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Om du har följt alla steg för att installera [!DNL Insight Server] (se [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)) har du kanske redan en [!DNL Transform] i katalogen Profiles.

1. Använd följande steg för att uppdatera [!DNL profile.cfg] för den profil som du vill använda [!DNL Transform]. Datauppsättningen bearbetas om när de här stegen har slutförts.

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. The [!DNL profile.cfg] visas.

   1. I [!DNL profile.cfg]fönster, högerklicka **[!UICONTROL Directories]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Om du vill lägga till den nya katalogen i slutet av kataloglistan högerklickar du på numret eller namnet på den sista katalogen i listan och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Ange namnet på den nya katalogen: [!DNL Transform]
   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager], högerklicka på bockmarkeringen för [!DNL profile.cfg] i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe (inklusive profilen), eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.
