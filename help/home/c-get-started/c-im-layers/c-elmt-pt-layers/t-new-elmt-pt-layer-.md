---
description: Steg för att göra ett elementpunktslager tillgängligt för visning på den globala visualiseringen.
title: Göra ett nytt elementpunktslager tillgängligt
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Gör ett nytt elementpunktslager tillgängligt{#make-a-new-element-point-layer-available}

Steg för att göra ett elementpunktslager tillgängligt för visning på den globala visualiseringen.

1. I mappen Profiler\*profilnamn*\Maps i Datans Workbench serverinstallationskatalog placerar du lagerfilen och den relaterade sökfilen.
1. Om du har definierat en ny dimension för elementpunktslagret och ännu inte har omformat datauppsättningen, omformar du datauppsättningen nu.
1. Redigera [!DNL order.txt]-filen i mappen Profiler\*profilnamn*\Maps för att återspegla i vilken ordning du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt]-filen ska du se till att inte visa mappningslager.

   Mer information om hur du använder [!DNL order.txt]-filer finns i kapitlet Konfigurera gränssnitt och analysfunktioner i *Datans Workbench användarhandbok*.

1. I Data Workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid Work Online.
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
