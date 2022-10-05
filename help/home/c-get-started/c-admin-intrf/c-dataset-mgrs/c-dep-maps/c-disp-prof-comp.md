---
description: Du kan välja att visa din profils datauppsättningskomponenter, frågemodellkomponenter eller arbetsytor, rapporter, menyalternativ och globala lager i beroendekartan.
title: Visa profilkomponenter
uuid: c904dcb7-6bb9-445c-be55-0573f88928ad
exl-id: 9d0aea02-cc24-43c2-afb8-e11ebd80e193
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---

# Visa profilkomponenter{#display-profile-components}

{{eol}}

Du kan välja att visa din profils datauppsättningskomponenter, frågemodellkomponenter eller arbetsytor, rapporter, menyalternativ och globala lager i beroendekartan.

**Välj de komponenter som ska visas**

1. Högerklicka i beroendekartan och klicka på **[!UICONTROL Display]**.
1. Välj ett eller flera av följande alternativ som ska visas på kartan. Ett X visas till vänster om varje visningsalternativ som du aktiverar.

   * **Datauppsättning** för att visa datauppsättningskomponenter. Se [Datauppsättningskomponenter](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293). Om du väljer att visa datauppsättningskomponenterna kan du välja att [!DNL Include File Blocks] på kartan. Se [Arbeta med filblock](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).

   * **Frågemodell** för att visa frågemodellkomponenter. Se [Frågemodellkomponenter](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).

   * **Arbetsytor och visualiseringar** för att visa arbetsytor, rapporter, menyalternativ och globala lager. Se [Arbetsytor och visualiseringar](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921). Det här alternativet fungerar bara om [!DNL Query Model] visningsalternativet är aktiverat.

>[!NOTE]
>
>Om [!DNL Query Model] visningsalternativet är inte aktiverat när du väljer [!DNL Workspaces and Visualizations] visas ett felmeddelande.

Om du inte kan se alla noder på kartan kan du flytta kartan, zooma in eller zooma ut för att visa hela kartan eller för att fokusera på ett visst avsnitt. Mer information om zoomning finns i [Zooma in visualiseringar](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

När du klickar på en nod markeras alla noder som är beroende av den noden och alla noder som den noden är beroende av, och deras namn visas.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>En markerad sökväg i en beroendekarta utgör inte en markering.

När du högerklickar på en nod kan du se identifieringsinformation om varje komponent som visas på kartan och välja menyalternativ som gör att du kan visa mer information om komponenten eller redigera komponenten. Dessutom kan du utföra textsökningar och visa prestandainformation för omformningar och utökade dimensioner.
