---
description: När du visar datauppsättningskomponenter på en beroendekarta kan du välja att aktivera visningsalternativet Inkludera filblock.
title: Filblock
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Filblock{#file-blocks}

{{eol}}

När du visar datauppsättningskomponenter på en beroendekarta kan du välja att aktivera visningsalternativet Inkludera filblock.

När det här alternativet är aktiverat visar kartan en enda blå nod för alla omformningar som definierats i en datauppsättningskonfigurationsfil och en enda grön nod för alla de utökade dimensioner som definierats i en datauppsättningskonfigurationsfil. Om t.ex. en [!DNL log processing dataset include] filen innehåller definitioner för tre omformningar. På kartan visas en blå nod som representerar de tre omformningarna. På samma sätt, om [!DNL transformation dataset include] filen innehåller definitioner av två utökade dimensioner. På kartan visas en grön nod som representerar de två utökade dimensionerna.

## Omformningsblock {#section-c442730394264a0b850792a32eaaa2da}

Varje blå nod är ett omformningsblock och har följande alternativ:

* Om du vill visa inmatningsfälten för omformningsblocket högerklickar du på noden för blocket och klickar **[!UICONTROL Inputs]**.
* Om du vill visa omvandlingsblockets utdatafält högerklickar du på noden för blocket och klickar på **[!UICONTROL Outputs]**.
* Om du vill redigera någon av omformningarna i blocket högerklickar du på noden för blocket och klickar på **[!UICONTROL Edit Configuration]**. Den bildtext som visas innehåller hela konfigurationsfilen i vilken alla omformningar definieras. Du kan sedan redigera parametrarna efter behov. Mer information om de här parametrarna finns i *Konfigurationshandbok för datauppsättning*.

* Om du vill visa alla omformningar i blocket högerklickar du på noden för omformningsblocket och klickar **[!UICONTROL Show Details]**. Den bildtext som visas innehåller ett annat beroendeschema som visar noder för alla omformningar i blocket.

## Dimension {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Varje grön nod är ett dimensionsblock och har följande alternativ:

* Om du vill visa inmatningsfälten eller den överordnade dimensionen för dimensionsblocket högerklickar du på noden för blocket och klickar **[!UICONTROL Inputs]**.
* Om du vill visa dimensioner för dimensionsblocket högerklickar du på noden för blocket och klickar på **[!UICONTROL Outputs]**.
