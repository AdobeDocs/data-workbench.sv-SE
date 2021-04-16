---
description: Steg för att göra eventuella terränglager tillgängliga för visning på webben.
title: Göra ett nytt terrängbildslager tillgängligt
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# Gör ett nytt terrängbildslager tillgängligt{#make-a-new-terrain-image-layer-available}

Steg för att göra eventuella terränglager tillgängliga för visning på webben.

1. I mappen Profiler\*profilnamn*\Maps i Datans Workbench serverinstallationskatalog placerar du lagerfilen och de bildfiler som stöds.
1. Redigera [!DNL order.txt]-filen i mappen Profiler\*profilnamn*\Maps för att återspegla i vilken ordning du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt]-filen ska du se till att inte visa mappningslager.

   Mer information om hur du använder [!DNL order.txt]-filer finns i kapitlet Konfigurera gränssnitt och analysfunktioner i *Datans Workbench användarhandbok*.

1. I Data Workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid Work Online.
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
