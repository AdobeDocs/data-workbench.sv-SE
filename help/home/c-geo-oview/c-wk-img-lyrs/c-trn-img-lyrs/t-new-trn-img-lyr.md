---
description: Steg för att göra ett nytt terränglager tillgängligt för visning på den globala visualiseringen.
solution: Analytics
title: Göra ett nytt Terrain-bildlager tillgängligt
topic: Data workbench
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Göra ett nytt Terrain-bildlager tillgängligt{#making-a-new-terrain-image-layer-available}

Steg för att göra ett nytt terränglager tillgängligt för visning på den globala visualiseringen.

1. I mappen Profiler\*profilnamn*\Maps i **[!UICONTROL Insight Server]** installationskatalogen placerar du lagerfilen och de bildfiler som stöds.
1. Redigera [!DNL order.txt] filen i mappen Profiler\*profilnamn*\Maps för att återspegla i vilken ordning du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt] filen bör du se till att inte visa mappningslager som du vill visa.

   Mer information om hur du använder [!DNL order.txt] filer finns i kapitlet Configuring Interface and Analysis Features i *Data Workbench User Guide*.

1. I data workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid [!DNL Work Online].
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.