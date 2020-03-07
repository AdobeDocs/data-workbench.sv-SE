---
description: Du kan välja att visa din profils datauppsättningskomponenter, frågemodellkomponenter eller arbetsytor, rapporter, menyalternativ och globala lager i beroendekartan.
solution: Analytics
title: Visa profilkomponenter
topic: Data workbench
uuid: c904dcb7-6bb9-445c-be55-0573f88928ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visa profilkomponenter{#display-profile-components}

Du kan välja att visa din profils datauppsättningskomponenter, frågemodellkomponenter eller arbetsytor, rapporter, menyalternativ och globala lager i beroendekartan.

**Välj de komponenter som ska visas**

1. Högerklicka i beroendekartan och klicka på **[!UICONTROL Display]**.
1. Välj ett eller flera av följande alternativ som ska visas på kartan. Ett X visas till vänster om varje visningsalternativ som du aktiverar.

   * **Datauppsättning** som visar datauppsättningskomponenter. Se [Datauppsättningskomponenter](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293). Om du väljer att visa datauppsättningskomponenterna kan du välja att göra det [!DNL Include File Blocks] på kartan. Se [Arbeta med filblock](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).

   * **Frågemodell** för att visa frågemodellkomponenter. Se [Frågemodellkomponenter](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).

   * **Arbetsytor och visualiseringar** för att visa arbetsytor, rapporter, menyalternativ och globala lager. Se [Arbetsytor och visualiseringar](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921). Det här alternativet fungerar bara om [!DNL Query Model] visningsalternativet är aktiverat.

>[!NOTE]
>
>Om [!DNL Query Model] visningsalternativet inte är aktiverat när du väljer [!DNL Workspaces and Visualizations] visningsalternativet visas ett felmeddelande.

Om du inte kan se alla noder på kartan kan du flytta kartan, zooma in eller zooma ut för att visa hela kartan eller för att fokusera på ett visst avsnitt. Mer information om zoomning finns i [Zooma i visualiseringar](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

När du klickar på en nod markeras alla noder som är beroende av den noden och alla noder som den noden är beroende av, och deras namn visas.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>En markerad sökväg i en beroendekarta utgör inte en markering.

När du högerklickar på en nod kan du se identifieringsinformation om varje komponent som visas på kartan och välja menyalternativ som gör att du kan visa mer information om komponenten eller redigera komponenten. Dessutom kan du utföra textsökningar och visa prestandainformation för omformningar och utökade dimensioner.
