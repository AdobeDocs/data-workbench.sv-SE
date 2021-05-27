---
description: Varje flik eller underflik i arbetsytan motsvarar en viss typ av information, t.ex. Dashboards, Activity (Aktivitet), Acquisition, osv.
title: Anpassa en arbetsflik
uuid: f1f557c8-f4cb-4789-8162-39cc7c52c943
exl-id: 529c6d8d-fc42-4c2b-a111-b8eea4665d8b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---

# Anpassa en arbetsflik{#customize-a-worktop-tab}

Varje flik eller underflik i arbetsytan motsvarar en viss typ av information, t.ex. Dashboards, Activity (Aktivitet), Acquisition, osv.

Fliken [!DNL Acquisition] kan till exempel innehålla arbetsytor som innehåller data om refererande domäner, sökmotorer och kampanjer.

Varje flik som visas i [!DNL Worktop] motsvarar en mapp i *arbetsprofilsnamnet*\Workspaces-mappen i Datans Workbench installationskatalog. Ordningen på flikarna i [!DNL Worktop] styrs av filen [!DNL order.txt] i samma mapp. Om du till exempel har en förvärvsundermapp i mappen Workspaces och sedan lägger till förvärvet som den första posten i filen [!DNL order.txt] är [!DNL Acquisition] den första fliken i [!DNL Worktop] och allt i den undermappen visas på fliken [!DNL Acquisition].

>[!NOTE]
>
>Mer information om hur du använder filen [!DNL order.txt] för att anpassa arbetsytans fönstermeny finns i [Anpassa menyer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/c-ctm-menus.md#concept-93d4c09cb7f34cd293b7b64fba1cf894).
