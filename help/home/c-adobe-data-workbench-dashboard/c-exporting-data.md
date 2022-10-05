---
description: Visar tre sätt att exportera data och hur du hämtar exporter.
title: Exporterar data
uuid: de37a60b-09db-4976-b427-f28b4697a8aa
exl-id: b581d617-62e7-4f39-84f3-853c0424bb3b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Exporterar data{#exporting-data}

{{eol}}

Visar tre sätt att exportera data och hur du hämtar exporter.

Data kan exporteras från kontrollpanelen på tre sätt.

Först kan du exportera data från en enskild visualisering. För det andra kan du exportera den aktuella arbetspanelen, inklusive alla konfigurationer och val du har gjort. För det tredje kan du exportera en sparad kontrollpanel utan att öppna den.

Exporten utförs i två steg. Först köas exporten på servern med någon av de tre metoderna ovan. Exportstatus visas i **[!UICONTROL Exports]** -menyn när exporten förbereds. När exporten är klar kan du sedan hämta data i CSV- eller Excel-format.

Export kan ta flera minuter, men du kan fortsätta att använda programmet under en export.

## Exportera visualiseringar {#section-46b74b46c2eb44129c8b85a9eabd2304}

Om du vill exportera data från en visualisering klickar du på **[!UICONTROL Save]** i visualiseringens verktygsmeny.

![](assets/export_visual.png)

Exporten initieras på servern och en exportindikator läggs till på menyn Exportera.

![](assets/export_queued.png)

## Exportera kontrollpaneler {#section-27329f2a5fed44b49deb26dc5164531f}

Välj **[!UICONTROL Export]** från **[!UICONTROL Dashboard]** -menyn.

![](assets/export_dashboard.png)

Exporten initieras på servern och en exportindikator läggs till på menyn Exportera.

## Exporterar sparade instrumentpaneler {#section-e989f7b16e25479ab77454f2c34471ba}

Om du vill starta en dataexport från en sparad kontrollpanel använder du kontrollpanelens webbläsare. Bläddra till den instrumentpanel du vill använda i Dashboard Browser och markera den så att instrumentpanelens information visas. På den högra informationspanelen, under **[!UICONTROL Operations]** avsnitt, markera **[!UICONTROL Export Data]**.

Exporten initieras på servern och en exportindikator läggs till i **[!UICONTROL Exports]** meny .

## Hämtar export {#section-0f03c5321c804867b7c72cf92f6f67d0}

När exporten är klar visas ett popup-meddelande om att exporten är klar.

![](assets/export_ready.png)

Om du vill hämta exporten använder du **[!UICONTROL Exports]** -menyn. Om du klickar på den gröna bockmarkeringen till höger om alternativet för den önskade exporten visas en listruta. På den här menyn, under **[!UICONTROL Save Export As…]** väljer du lämpligt menyalternativ för att hämta exporten i antingen CSV- eller Excel-format.

![](assets/export_save_as.png)

Filnedladdningen i webbläsaren startas nu.

Exporterna tas inte bort automatiskt, så du kan enkelt hämta exporten i varje format. Du kan ta bort exporter från **[!UICONTROL Exports]** i den vänstra navigeringspanelen. Annars tas de bort automatiskt när du loggar ut.

Så här tar du bort en export från **[!UICONTROL Export List]** klickar du på bockmarkeringen till höger om exportrubriken och väljer **[!UICONTROL Remove From List]**.

![](assets/export_remove_from_list.png)
