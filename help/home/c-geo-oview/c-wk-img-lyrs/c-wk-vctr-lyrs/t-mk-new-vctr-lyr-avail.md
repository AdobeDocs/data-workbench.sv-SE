---
description: Steg för att göra ett vektorlager tillgängligt för visning på den globala visualiseringen.
title: Göra ett nytt vektorlager tillgängligt
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# Göra ett nytt vektorlager tillgängligt{#making-a-new-vector-layer-available}

{{eol}}

Steg för att göra ett vektorlager tillgängligt för visning på den globala visualiseringen.

1. Placera lagerfilen och [!DNL .vec] eller [!DNL .tsv] filer.
1. Redigera [!DNL order.txt] i mappen Profiler\*profilnamn*\Mappar i den ordning som du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt] ska du se till att inte visa mappningslager som du vill visa.

   Mer information om hur du använder [!DNL order.txt] -filer, se kapitlet Konfigurera gränssnitt och analysfunktioner i *Användarhandbok för Data Workbench*.

1. I data workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid [!DNL Work Online].
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
