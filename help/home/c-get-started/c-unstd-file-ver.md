---
description: Med arbetsytan är det enkelt att avgöra var varje arbetsyta är lagrad, oavsett om den finns på Datan Workbench, på den lokala datorn eller båda.
title: Filversionshantering
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
exl-id: 82a70d51-a95c-4ddd-8d3c-cd0364940693
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Filversionshantering{#file-versioning}

Med arbetsytan är det enkelt att avgöra var varje arbetsyta är lagrad, oavsett om den finns på Datan Workbench, på den lokala datorn eller båda.

## Identifiera filversioner {#section-d555c96b016344f19b356c12213dd2a9}

**Server**

En serverarbetsyta lagras på den anslutna Datan Workbench och är tillgänglig för alla användare som har tillgång till den här profilen och fliken. En serverarbetsyta visas som en enda miniatyrbild.

![](assets/wsp_thumb_server.png)

Serverarbetsytor lagras som standard i lämplig undermapp i Workspaces-mappen på den anslutna Datan Workbench.

**Lokal**

En lokal arbetsyta är den lokala versionen av en serverarbetsyta. En lokal arbetsyta visas som två överlappande miniatyrbilder. Miniatyrbilden högst upp är från början omgiven av en glöd, vilket anger att nyligen gjorda ändringar har gjorts lokalt på serverarbetsytan. Den här glöden försvinner över tid.

![](assets/wsp_thumb_local.png)

Lokala arbetsytor lagras som standard i namnmappen [!DNL User\working profile name\Workspaces\tab] i installationskatalogen för Data Workbench (eller Insight).

>[!NOTE]
>
>När du har en lokal version av en serverarbetsyta måste du återgå till serverversionen innan du kan hämta en uppdaterad version av serverarbetsytan. Om du vill återgå till serverversionen utan lokala ändringar högerklickar du på miniatyrbilden för den lokala arbetsytan och klickar på **[!UICONTROL Revert to server version]**.

**Användare**

En användararbetsyta är en arbetsyta som skapades på och som bara finns på den lokala datorn. En användararbetsyta visas som en enda miniatyrbild med en prickad kontur av en tom arbetsyta bakom, vilket anger att det inte finns någon källarbetsyta på den anslutna Datan Workbench.

![](assets/wsp_thumb_user.png)

Arbetsytor för användare lagras som standard i mappen User\*workprofile name*\Workspaces\*tab name* i installationskatalogen för Insight.
