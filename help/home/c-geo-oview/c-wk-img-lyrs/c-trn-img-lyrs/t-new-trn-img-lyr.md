---
description: Steg för att göra ett nytt terränglager tillgängligt för visning på den globala visualiseringen.
title: Göra ett nytt Terrain-bildlager tillgängligt
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 0%

---

# Göra ett nytt Terrain-bildlager tillgängligt{#making-a-new-terrain-image-layer-available}

{{eol}}

Steg för att göra ett nytt terränglager tillgängligt för visning på den globala visualiseringen.

1. I mappen Profiler\*profilnamn*\Maps i mappen **[!UICONTROL Insight Server]** installationskatalogen placerar du lagerfilen och de bildfiler som stöds.
1. Redigera [!DNL order.txt] i mappen Profiler\*profilnamn*\Mappar i den ordning som du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt] ska du se till att inte visa mappningslager som du vill visa.

   Mer information om hur du använder [!DNL order.txt] -filer, se kapitlet Konfigurera gränssnitt och analysfunktioner i *Användarhandbok för Data Workbench*.

1. I data workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid [!DNL Work Online].
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
