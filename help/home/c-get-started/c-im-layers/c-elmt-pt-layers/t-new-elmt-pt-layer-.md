---
description: Steg för att göra ett elementpunktslager tillgängligt för visning på den globala visualiseringen.
solution: Analytics
title: Göra ett nytt elementpunktslager tillgängligt
topic: Data workbench
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Göra ett nytt elementpunktslager tillgängligt{#make-a-new-element-point-layer-available}

Steg för att göra ett elementpunktslager tillgängligt för visning på den globala visualiseringen.

1. I mappen Profiler\*profilnamn*\Maps i installationskatalogen för Data Workbench-servern placerar du lagerfilen och den relaterade sökfilen.
1. Om du har definierat en ny dimension för elementpunktslagret och ännu inte har omformat datauppsättningen, omformar du datauppsättningen nu.
1. Redigera [!DNL order.txt] filen i mappen Profiler\*profilnamn*\Maps för att återspegla i vilken ordning du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt] filen bör du se till att inte visa mappningslager som du vill visa.

   Mer information om hur du använder [!DNL order.txt] filer finns i kapitlet Configuring Interface and Analysis Features i *Data Workbench User Guide*.

1. I Data Workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid Work Online.
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.