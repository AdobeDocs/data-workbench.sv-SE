---
description: Steg för att göra ett vektorlager tillgängligt för visning på den globala visualiseringen.
title: Göra ett nytt vektorlager tillgängligt
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# Göra ett nytt vektorlager tillgängligt{#making-a-new-vector-layer-available}

Steg för att göra ett vektorlager tillgängligt för visning på den globala visualiseringen.

1. Placera lagerfilen och [!DNL .vec]- eller [!DNL .tsv]-filerna i mappen Profiler\*profilnamn*\Maps i installationskatalogen för Data Workbench-servern.
1. Redigera [!DNL order.txt]-filen i mappen Profiler\*profilnamn*\Maps för att återspegla i vilken ordning du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt]-filen ska du se till att inte visa mappningslager.

   Mer information om hur du använder [!DNL order.txt]-filer finns i kapitlet Konfigurera gränssnitt och analysfunktioner i *Datans Workbench användarhandbok*.

1. I data workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid [!DNL Work Online].
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
