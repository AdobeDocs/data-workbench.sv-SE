---
description: Så här exporterar, kopierar och bokmärker du från skrivbordet.
title: Använda menyn Arbetsminiatyrbilder
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# Använda menyn Arbetsminiatyrbilder{#using-the-worktop-thumbnail-menu}

{{eol}}

Så här exporterar, kopierar och bokmärker du från skrivbordet.

Högerklicka på en arbetsyta för att exportera, kopiera och bokmärka funktioner från arbetsytan.

![](assets/thumbnail_menu.png)

## Gränssnittsbeskrivningar {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Följande element är tillgängliga i [!DNL Worktop] miniatyrmeny:

**Serverarbetsyta:** *name*

Visas endast för oredigerade serverarbetsytor. Identifierar den namngivna arbetsytan som samma som arbetsytan på servern.

**Datum:** *dag och tid*

Datum och tid då arbetsytan senast öppnades.

**Lokal version av:** *name*

Visas endast för lokala versioner av serverarbetsytor. Identifierar den namngivna arbetsytan som en redigerad, lokal version av en arbetsyta som lagras på servern.

**Användararbetsyta:** *name*

Visas endast för användararbetsytor. Identifierar den namngivna arbetsytan som en arbetsyta som bara finns på den lokala datorn.

**Beräkna i bakgrunden**

Visas bara när du arbetar online. Behåller frågorna i den valda arbetsytan som körs i bakgrunden medan du fortsätter arbeta. När du väljer det här alternativet visas följande information i miniatyrbilden, som anger frågeförloppet:

* Arbetar: *n%* - anger att frågan bearbetas och hur stor procentandel av bearbetningen som är slutförd.
* *n* MB Läs in fråga - frågeresultatets totala storlek. Frågebelastningen är proportionerlig till den totala minnesbelastningen på Datan Workbench, men korrelerar inte direkt. Som vägledning kan en belastning på 10 MB eller mer belasta systemet. Den listade frågelasten tar inte hänsyn till kluster.

   >[!NOTE]
   >
   >Om Beräkna i bakgrunden förblir markerat blir frågorna i den valda arbetsytan ständiga frågor, fortsätter att uppdateras och använder minnesinläsning. Avmarkera alternativet Beräkna i bakgrunden när du är klar med arbetsytan.

**Exportera till Excel**

Exportera arbetsytedata till tabeller i Microsoft Excel (.xls- och .xslx-filer). När du exporterar en arbetsyta till Excel exporteras data från vissa visualiseringar, dimensions- och värdesförklaringar samt textanteckningar till en ny Excel-arbetsbok med en visualisering per kalkylblad.

**Exportera till Excel-mall**

Exportera till en Excel-mall (.xltx).

**Kopiera**

Kopierar arbetsytan. Mer information om hur du klistrar in en kopierad arbetsyta finns i [Kopiera och klistra in befintliga arbetsytor](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Återställ till serverversion**

Visas endast för lokala versioner av serverarbetsytor. Tar bort den lokala kopian av den här arbetsytan. Originalet finns kvar på servern.

**Ta bort**

Visas endast för användararbetsytor. Tar bort användarens arbetsyta, som bara finns på den lokala datorn. Mer information om hur du tar bort arbetsytor från den anslutna Datan Workbench finns i [Tar bort filer från din arbetsprofil](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**Spara på server**

Visas endast för lokala versioner av serverarbetsytor och användararbetsytor och fungerar bara för de användare som har rätt behörighet. Sparar den lokala kopian av arbetsytan på servern. Som standard sparas arbetsytorna i lämplig arbetsyta `<profile name>\Workspaces\<tab name>` mapp.

**Bokmärke**

Skapa ett bokmärke för en arbetsyta som snabbt kan hämtas senare.

En bokmärkesikon ![](assets/bookmark_icon.png) visas ovanför arbetsytan på arbetsytan och arbetsytans namn visas på bokmärkespanelen. ![](assets/bookmark_worktop.png)
