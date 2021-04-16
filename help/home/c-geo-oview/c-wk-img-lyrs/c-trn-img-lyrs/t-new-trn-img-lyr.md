---
description: Steg för att göra ett nytt terränglager tillgängligt för visning på den globala visualiseringen.
title: Göra ett nytt Terrain-bildlager tillgängligt
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 0%

---

# Göra ett nytt terrängbildlager tillgängligt{#making-a-new-terrain-image-layer-available}

Steg för att göra ett nytt terränglager tillgängligt för visning på den globala visualiseringen.

1. Placera lagerfilen och de bildfiler som stöds i mappen Profiler\*profilnamn*\Maps i installationskatalogen för **[!UICONTROL Insight Server]**.
1. Redigera [!DNL order.txt]-filen i mappen Profiler\*profilnamn*\Maps för att återspegla i vilken ordning du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt]-filen ska du se till att inte visa mappningslager.

   Mer information om hur du använder [!DNL order.txt]-filer finns i kapitlet Konfigurera gränssnitt och analysfunktioner i *Datans Workbench användarhandbok*.

1. I data workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid [!DNL Work Online].
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
