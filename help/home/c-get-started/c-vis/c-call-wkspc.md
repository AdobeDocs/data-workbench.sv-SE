---
description: Bildtexter är fönster som du lägger till på en arbetsyta för att uppmärksamma ett visst dimensionselement genom att skapa en ny visualisering med ett virtuellt urval av det elementet.
title: Lägga till bildtexter på en arbetsyta
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
exl-id: fcdb9231-d44a-4287-b799-6a66f7f79432
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Lägga till bildtexter på en arbetsyta{#adding-callouts-to-a-workspace}

{{eol}}

Bildtexter är fönster som du lägger till på en arbetsyta för att uppmärksamma ett visst dimensionselement genom att skapa en ny visualisering med ett virtuellt urval av det elementet.

Data Workbench levereras med en standarduppsättning med bildtexttyper. Eftersom implementeringen kan anpassas helt kan de tillgängliga bildtexttyperna som visas i implementeringen skilja sig från vad som beskrivs i den här handboken.

Som standard innehåller Data Workbench följande bildtexter:

* [Anteckning](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d)
* [Tomt linjediagram](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Tomt punktdiagram](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Tom tabell](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Förklaring till förtroende](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791)
* [Metrisk förklaring](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>Bildtexter fungerar inte som markeringar (d.v.s. de påverkar inte andra visualiseringar på arbetsytan) om du inte markerar något i bildtexten.

Du kan lägga till eller redigera bildtextdefinitioner genom att konfigurera bildtextfilerna i dialogrutan *profilnamn*\Context\Callout folder of the [!DNL Server] installationsmapp. Se [Konfigurerar bildtexter](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a).

## Lägga till en anteckningsbubbla i en visualisering {#section-7b6742160b3f4aed872a09c8c023f90d}

1. Högerklicka på elementet som du vill skapa en bildtext för och klicka sedan på **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]** eller **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**. Ett tomt fönster visas med en synlig anslutning till det elementet.

   ![](assets/client-call.png)

   Om du vill lägga till hänvisningar till grafiska visualiseringar måste du högerklicka längst ned i visualiseringen (basaxeln) för att öppna en meny.

   ![](assets/visualization_callout_linegraph.png)

1. Beroende på vad du väljer slutför du lämpligt steg:

   * För en textanteckning skriver eller klistrar du in den önskade texten i bildtexten och formaterar sedan texten. Se [Arbeta med textanteckningar](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * För en bildanteckning klistrar du in bilden i bildtexten genom att kopiera bilden och sedan högerklickar i bildtexten. Klicka på **[!UICONTROL Paste image]**. Se [Arbeta med bildanteckningar](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962).

## Lägga till en tom bildtext för tabeller, linjediagram eller punktdiagram i en visualisering {#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. Högerklicka på elementet som du vill skapa en bildtext för och klicka på **[!UICONTROL Add Callout]** > *&lt;**[!UICONTROL callout type]**>*.

   I följande exempel visas en tom tabellpratbubbla.

   ![](assets/vis_callout_blank_bar_graph.png)

1. Om du vill välja en dimension högerklickar du **[!UICONTROL None]** och klicka **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

   >[!NOTE]
   >
   >Om du ändrar dimensionen i en visualisering som har en bildtext, ändras bildtexten från att vara ansluten till elementet i den ursprungliga dimensionen till att vara ansluten till hela visualiseringen.

## Lägga till en förklarande förklaring till en visualisering {#section-386d1293ddc24a0c9cccb332e20db791}

1. Högerklicka på elementet som du vill skapa bildtexten för och klicka på **[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**.

   ![](assets/vis_callout_confidenceLegend.png)

1. Ändra [!DNL Metric or Formula] fält.

Mer information om syntaxregler för uttryck finns i [Syntax för frågespråk](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f). Se [Bekräftelseförklaringar](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd).

## Lägga till en måttförklarande bildtext i en visualisering {#section-daa6d372c22246d9827880a9d6e804d8}

1. Högerklicka på elementet som du vill skapa bildtexten för och klicka på **[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**.

   ![](assets/vis_callout_metricLegend.png)

1. Om du vill kan du lägga till eller ta bort mått från måttteckenförklaringen.

Se [Metriska förklaringar](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
