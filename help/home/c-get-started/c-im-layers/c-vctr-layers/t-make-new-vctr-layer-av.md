---
description: Steg för att göra alla vektorlager tillgängliga för visning på den globala visualiseringen.
title: Göra ett nytt vektorlager tillgängligt
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---

# Göra ett nytt vektorlager tillgängligt{#make-a-new-vector-layer-available}

{{eol}}

Steg för att göra alla vektorlager tillgängliga för visning på den globala visualiseringen.

1. I mappen Profiler\*profilnamn*\Maps i Datans Workbench serverinstallationskatalog placerar du lagerfilen och [!DNL .vec] eller [!DNL .tsv] filer.
1. Redigera [!DNL order.txt] i mappen Profiler\*profilnamn*\Mappar i den ordning som du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt] ska du se till att inte visa mappningslager som du vill visa.

   Mer information om hur du använder [!DNL order.txt] filer, se [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. I Insight väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid Work Online.
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
