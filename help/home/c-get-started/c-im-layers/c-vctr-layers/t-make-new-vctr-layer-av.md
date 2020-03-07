---
description: Steg för att göra alla vektorlager tillgängliga för visning på den globala visualiseringen.
solution: Analytics
title: Göra ett nytt vektorlager tillgängligt
topic: Data workbench
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Göra ett nytt vektorlager tillgängligt{#make-a-new-vector-layer-available}

Steg för att göra alla vektorlager tillgängliga för visning på den globala visualiseringen.

1. I mappen Profiler\*profilnamn*\Maps i Data Workbench-serverns installationskatalog placerar du lagerfilen och [!DNL .vec] eller [!DNL .tsv] filerna.
1. Redigera [!DNL order.txt] filen i mappen Profiler\*profilnamn*\Maps för att återspegla i vilken ordning du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt] filen bör du se till att inte visa mappningslager som du vill visa.

   Mer information om hur du använder [!DNL order.txt] filer finns i [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. I Insight väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid Work Online.
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
