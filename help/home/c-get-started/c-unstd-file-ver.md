---
description: Med arbetsytan är det enkelt att avgöra var varje arbetsyta lagras, oavsett om den finns på Data Workbench-servern, på den lokala datorn eller båda.
solution: Analytics
title: Filversionshantering
topic: Data workbench
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filversionshantering{#file-versioning}

Med arbetsytan är det enkelt att avgöra var varje arbetsyta lagras, oavsett om den finns på Data Workbench-servern, på den lokala datorn eller båda.

## Identifiera filversioner {#section-d555c96b016344f19b356c12213dd2a9}

**Server**

En serverarbetsyta lagras på den anslutna Data Workbench-servern och är tillgänglig för alla användare som har tillgång till den här profilen och fliken. En serverarbetsyta visas som en enda miniatyrbild.

![](assets/wsp_thumb_server.png)

Serverarbetsytor lagras som standard i lämplig undermapp i mappen Workspaces på den anslutna Data Workbench-servern.

**Lokal**

En lokal arbetsyta är den lokala versionen av en serverarbetsyta. En lokal arbetsyta visas som två överlappande miniatyrbilder. Miniatyrbilden högst upp är från början omgiven av en glöd, vilket anger att nyligen gjorda ändringar har gjorts lokalt på serverarbetsytan. Den här glöden försvinner över tid.

![](assets/wsp_thumb_local.png)

Lokala arbetsytor lagras som standard i [!DNL User\working profile name\Workspaces\tab] namnmappen i installationskatalogen för Data Workbench (eller Insight).

>[!NOTE]
>
>När du har en lokal version av en serverarbetsyta måste du återgå till serverversionen innan du kan hämta en uppdaterad version av serverarbetsytan. Om du vill återgå till serverversionen utan lokala ändringar högerklickar du på miniatyrbilden för den lokala arbetsytan och klickar på **[!UICONTROL Revert to server version]**.

**Användare**

En användararbetsyta är en arbetsyta som skapades på och som bara finns på den lokala datorn. En användararbetsyta visas som en enda miniatyrbild med en prickad kontur av en tom arbetsyta bakom, vilket anger att det inte finns någon källarbetsyta på den anslutna Data Workbench-servern.

![](assets/wsp_thumb_user.png)

Arbetsytor för användare lagras som standard i mappen User\*workprofile name*\Workspaces\*tab name* i installationskatalogen för Insight.
