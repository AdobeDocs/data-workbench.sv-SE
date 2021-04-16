---
description: När du visar datauppsättningskomponenter på en beroendekarta kan du välja att aktivera visningsalternativet Inkludera filblock.
title: Filblock
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Filblock{#file-blocks}

När du visar datauppsättningskomponenter på en beroendekarta kan du välja att aktivera visningsalternativet Inkludera filblock.

När det här alternativet är aktiverat visar kartan en enda blå nod för alla omformningar som definierats i en datauppsättningskonfigurationsfil och en enda grön nod för alla de utökade dimensioner som definierats i en datauppsättningskonfigurationsfil. Om en [!DNL log processing dataset include]-fil till exempel innehåller definitionerna för tre omformningar, visar kartan en blå nod som representerar de tre omformningarna. Om en [!DNL transformation dataset include]-fil innehåller definitioner för två utökade dimensioner visas på samma sätt en grön nod som representerar de två utökade dimensionerna.

## Omformningsblock {#section-c442730394264a0b850792a32eaaa2da}

Varje blå nod är ett omformningsblock och har följande alternativ:

* Om du vill visa indatafälten för omformningsblocket högerklickar du på noden för blocket och klickar på **[!UICONTROL Inputs]**.
* Om du vill visa omvandlingsblockets utdatafält högerklickar du på noden för blocket och klickar på **[!UICONTROL Outputs]**.
* Om du vill redigera någon av omformningarna i blocket högerklickar du på noden för blocket och klickar på **[!UICONTROL Edit Configuration]**. Den bildtext som visas innehåller hela konfigurationsfilen i vilken alla omformningar definieras. Du kan sedan redigera parametrarna efter behov. Mer information om de här parametrarna finns i *Konfigurationshandboken för datauppsättningar*.

* Om du vill visa alla omformningar i blocket högerklickar du på noden för omformningsblocket och klickar på **[!UICONTROL Show Details]**. Den bildtext som visas innehåller ett annat beroendeschema som visar noder för alla omformningar i blocket.

## Dimensioner {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Varje grön nod är ett dimensionsblock och har följande alternativ:

* Om du vill visa indatafälten eller den överordnade dimensionen för dimensionsblocket högerklickar du på noden för blocket och klickar på **[!UICONTROL Inputs]**.
* Om du vill visa dimensioner för dimensionsblocket högerklickar du på noden för blocket och klickar på **[!UICONTROL Outputs]**.
