---
description: Med hjälp av beroendekartor kan du visualisera och hantera konfigurationen för komponenterna i din profil.
solution: Analytics
title: Beroendekartor
topic: Data workbench
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Beroendekartor{#dependency-maps}

Med hjälp av beroendekartor kan du visualisera och hantera konfigurationen för komponenterna i din profil.

* **Datauppsättningskomponenter:** Logga källor, filter, fält, omformningar och utökade dimensioner som definieras i datauppsättningens [!DNL Log Processing.cfg], [!DNL Transformation.cfg]och [!DNL dataset include] filer.

* **Frågemodellkomponenter:** Mätvärden, dimensioner och filter som definieras i mapparna Dimensioner, Mätvärden och Filter.
* **Arbetsytor och visualiseringar:** Arbetsytor, rapporter, menyalternativ och globala lager.

Mer information om hur du arbetar med frågemodellkomponenter, arbetsytor och visualiseringar i beroendekartor finns i användarhandboken för *Data Workbench*.

Profilkomponenter representeras av färgade punkter (noder) på kartan. Linjerna som förbinder noderna avbildar beroenden, det vill säga hur komponenterna relaterar till varandra. En linje mellan två noder innebär att utdata för noden till vänster är indata för noden till höger, det vill säga att den högra noden är beroende av den vänstra noden.

## Visa datauppsättningskomponenter {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. Högerklicka i beroendekartan och klicka på **[!UICONTROL Display]**.
1. Välj **[!UICONTROL Dataset]**. Ett X visas till vänster om [!DNL Dataset].

Mer information om andra visningsalternativ finns i användarhandboken för *Data Workbench*.

I bilden nedan visas en beroendekarta vars noder representerar en datamängds loggkällor, fält, omformningar och utökade dimensioner.

![](assets/vis_DependencyMap.png)

* En gulgrön nod representerar en eller flera loggkällor eller ett filter som definieras i datauppsättningen. En nod för en loggkälla visas alltid längst till vänster på kartan.
* En grå nod representerar ett fält som listas i parametern Fält i en [!DNL Log Processing.cfg] eller [!DNL Log Processing Include]fil.

* En blå nod representerar en omformning.
* En grön nod representerar en utökad dimension.

>[!NOTE]
>
>Om datauppsättningen har en enda loggkälla visas loggkällan på kartan: *loggkällans namn*. Om datauppsättningen har flera loggkällor visas *antal* loggkällor på kartan, där antal är antalet loggkällor. Om du t.ex. har tre loggkällor i datauppsättningen visas 3 loggkällor på kartan.

Om du inte kan se alla noder på kartan kan du flytta kartan, zooma in eller zooma ut för att visa hela kartan eller för att fokusera på ett visst avsnitt. Mer information om zoomning finns i kapitlet Arbeta med visualiseringar i *användarhandboken* för Data Workbench.

När du klickar på en nod markeras alla noder som är beroende av den noden och alla noder som den noden är beroende av, och deras namn visas.

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>En markerad sökväg i en beroendekarta utgör inte en markering.

När du högerklickar på en nod kan du se identifieringsinformation om varje komponent som visas på kartan och välja menyalternativ som gör att du kan visa mer information om komponenten eller redigera komponenten. Dessutom kan du utföra textsökningar och visa prestandainformation för omformningar och utökade dimensioner.

Mer information om de här funktionerna för beroendekartor finns i kapitlet Administrativa gränssnitt i användarhandboken för *Data Workbench*.
