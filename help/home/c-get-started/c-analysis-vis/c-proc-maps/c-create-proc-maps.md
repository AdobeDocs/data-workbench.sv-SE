---
description: Du kan skapa 2D- och 3D-processkartor genom att dra och släppa element från stapeldiagram, tabeller och hierarkivvyer till en tom karta.
title: Skapa en processkarta
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
exl-id: 2e417a8e-5b1c-4dce-9e4e-ac7ed044564c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Skapa en processkarta{#create-a-process-map}

Du kan skapa 2D- och 3D-processkartor genom att dra och släppa element från stapeldiagram, tabeller och hierarkivvyer till en tom karta.

De element som du kan lägga till måste vara element i processmappningens basdimension. Du kan också dra och släppa noder från en processkarta till en annan så länge som kartorna använder samma basdimension. Dessutom kan hela kartan zoomas eller flyttas för att fokusera på en viss nod, eller så kan den ändras till andra visualiseringstyper. Se [Zooma in visualiseringar](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**Lägga till element i en processkarta med hjälp av ett tabell- eller stolpdiagram**

* Från alla tabeller eller stolpdiagram med samma basdimension som processkartan trycker du på Ctrl+Alt samtidigt som du klickar och drar enskilda element till processkartan. Markören visar ordet &quot;Nej&quot; tills musen når processkartan.

   >[!NOTE]
   >
   >De element som du kan lägga till måste vara element i processmappningens basdimension.

   ![](assets/vis_2DProcessMap_addPages.png)

**Lägga till element i en processkarta med hjälp av en hierarkisk vy**

>[!NOTE]
>
>Adobe rekommenderar att du lägger till noder från den högsta nivån i hierarkin som du analyserar.

1. Högerklicka på ett element eller etiketten för basdimensionen från en tabell eller ett stolpdiagram med samma basdimension som processkartan och klicka på **[!UICONTROL Hierarchy View]**.
1. Tryck på Ctrl+Alt medan du klickar och drar element till processkartan. Markören visar ordet &quot;Nej&quot; tills musen når kartan.

   >[!NOTE]
   >
   >De element som du kan lägga till måste vara element i processmappningens basdimension.

   Om du drar ett enskilt element till en processkarta skapas en mappningsnod för endast det elementet, men om du markerar flera element (en grupp) eller en mapp som innehåller flera element skapas en enda nod för gruppen eller mappen om du drar från hierarkin. Om du till exempel arbetar med webbplatsdata och drar en mapp med namnet [!DNL site.com/cgi-bin] till en karta skapas en nod med namnet [!DNL site.com/cgi-bin/*], som representerar alla sidor och kataloger som är underordnade den mappen.

Mer information om sidhierarkivyer finns i [Använda hierarkivyer](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff).

**Lägga till noder i en processkarta från en annan processkarta**

>[!NOTE]
>
>Processkartorna måste ha samma grunddimension.

* Kopiera en nod från den första till den andra processkartan med följande metoder:

   * Om du vill kopiera enskilda noder klickar du på och drar varje nod till den andra processkartan.
   * Om du vill kopiera flera noder Ctrl-klickar och drar du för att skapa en ruta runt de noder du vill kopiera. Klicka sedan och dra de markerade noderna till den andra processkartan. Alla markerade noder kopieras till den andra processkartan.
