---
description: Med hjälp av beroendekartor kan du visualisera och hantera konfigurationen för komponenterna i din profil.
title: Beroendekartor
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# Beroendekartor{#dependency-maps}

Med hjälp av beroendekartor kan du visualisera och hantera konfigurationen för komponenterna i din profil.

* **Datauppsättningskomponenter:** Loggkällor, filter, fält, omformningar och utökade dimensioner som definieras i datauppsättningens  [!DNL Log Processing.cfg],  [!DNL Transformation.cfg]och  [!DNL dataset include] filer.

* **Frågemodellkomponenter:** Mätvärden, dimensioner och filter som definieras i mapparna Dimensioner, Metrisk och Filter.
* **Arbetsytor och visualiseringar:** Arbetsytor, rapporter, menyalternativ och globala lager.

Mer information om hur du arbetar med frågemodellkomponenter, arbetsytor och visualiseringar i beroendekartor finns i *Datans Workbench användarhandbok*.

Profilkomponenter representeras av färgade punkter (noder) på kartan. Linjerna som förbinder noderna avbildar beroenden, det vill säga hur komponenterna relaterar till varandra. En linje mellan två noder innebär att utdata för noden till vänster är indata för noden till höger, det vill säga att den högra noden är beroende av den vänstra noden.

## Visar datauppsättningskomponenter {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Högerklicka i beroendekartan och klicka på **[!UICONTROL Display]**.
1. Välj **[!UICONTROL Dataset]**. Ett X visas till vänster om [!DNL Dataset].

Mer information om andra visningsalternativ finns i *Datans Workbench användarhandbok*.

I bilden nedan visas en beroendekarta vars noder representerar en datamängds loggkällor, fält, omformningar och utökade dimensioner.

![](assets/vis_DependencyMap.png)

* En gulgrön nod representerar en eller flera loggkällor eller ett filter som definieras i datauppsättningen. En nod för en loggkälla visas alltid längst till vänster på kartan.
* En grå nod representerar ett fält som visas i fältparametern i en [!DNL Log Processing.cfg]- eller [!DNL Log Processing Include]fil.

* En blå nod representerar en omformning.
* En grön nod representerar en utökad dimension.

>[!NOTE]
>
>Om datauppsättningen har en enda loggkälla visas loggkällan på kartan: *loggkällans namn*. Om datauppsättningen har flera loggkällor visas *number* loggkällor på kartan, där siffran är antalet loggkällor. Om du t.ex. har tre loggkällor i datauppsättningen visas 3 loggkällor på kartan.

Om du inte kan se alla noder på kartan kan du flytta kartan, zooma in eller zooma ut för att visa hela kartan eller för att fokusera på ett visst avsnitt. Mer information om zoomning finns i kapitlet Arbeta med visualiseringar i *Datans Workbench användarhandbok*.

När du klickar på en nod markeras alla noder som är beroende av den noden och alla noder som den noden är beroende av, och deras namn visas.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>En markerad sökväg i en beroendekarta utgör inte en markering.

När du högerklickar på en nod kan du se identifieringsinformation om varje komponent som visas på kartan och välja menyalternativ som gör att du kan visa mer information om komponenten eller redigera komponenten. Dessutom kan du utföra textsökningar och visa prestandainformation för omformningar och utökade dimensioner.

Mer information om de här funktionerna för beroendekartor finns i kapitlet Administrativa gränssnitt i *Datans Workbench användarhandbok*.
