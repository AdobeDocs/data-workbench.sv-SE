---
description: Steg för att göra ett elementpunktslager tillgängligt för visning på den globala visualiseringen.
title: Göra ett nytt elementpunktslager tillgängligt
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Göra ett nytt elementpunktslager tillgängligt{#make-a-new-element-point-layer-available}

{{eol}}

Steg för att göra ett elementpunktslager tillgängligt för visning på den globala visualiseringen.

1. I mappen Profiler\*profilnamn*\Maps i Datans Workbench serverinstallationskatalog placerar du lagerfilen och den relaterade sökfilen.
1. Om du har definierat en ny dimension för elementpunktslagret och ännu inte har omformat datauppsättningen, omformar du datauppsättningen nu.
1. Redigera [!DNL order.txt] i mappen Profiler\*profilnamn*\Mappar i den ordning som du vill att lagren ska visas. Som standard visas lager i lexikografisk ordning efter namn.

   >[!NOTE]
   >
   >När du redigerar [!DNL order.txt] ska du se till att inte visa mappningslager som du vill visa.

   Mer information om hur du använder [!DNL order.txt] -filer, se kapitlet Konfigurera gränssnitt och analysfunktioner i *Användarhandbok för Data Workbench*.

1. I Data Workbench väljer du önskad profil genom att högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Work Online]**. Ett X visas bredvid Work Online.
1. Öppna en arbetsyta och en global visualisering, högerklicka och välj det nya lagret. Ett X visas bredvid lagernamnet.
