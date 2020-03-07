---
description: Visar tre sätt att exportera data och hur du hämtar exporter.
solution: Analytics
title: Exporterar data
topic: Data workbench
uuid: de37a60b-09db-4976-b427-f28b4697a8aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exporterar data{#exporting-data}

Visar tre sätt att exportera data och hur du hämtar exporter.

Data kan exporteras från kontrollpanelen på tre sätt.

Först kan du exportera data från en enskild visualisering. För det andra kan du exportera den aktuella arbetspanelen, inklusive alla konfigurationer och val du har gjort. För det tredje kan du exportera en sparad kontrollpanel utan att öppna den.

Exporten utförs i två steg. Först köas exporten på servern med någon av de tre metoderna ovan. Exportstatus visas på **[!UICONTROL Exports]** menyn när exporten förbereds. När exporten är klar kan du sedan hämta data i CSV- eller Excel-format.

Export kan ta flera minuter, men du kan fortsätta att använda programmet under en export.

## Exportera visualiseringar {#section-46b74b46c2eb44129c8b85a9eabd2304}

Om du vill exportera data från en visualisering klickar du **[!UICONTROL Save]** på menyn för visualiseringsverktyget.

![](assets/export_visual.png)

Exporten initieras på servern och en exportindikator läggs till på menyn Exportera.

![](assets/export_queued.png)

## Exportera kontrollpaneler {#section-27329f2a5fed44b49deb26dc5164531f}

Om du vill starta en dataexport från en fungerande kontrollpanel väljer du **[!UICONTROL Export]** på **[!UICONTROL Dashboard]** menyn.

![](assets/export_dashboard.png)

Exporten initieras på servern och en exportindikator läggs till på menyn Exportera.

## Exporterar sparade instrumentpaneler {#section-e989f7b16e25479ab77454f2c34471ba}

Om du vill starta en dataexport från en sparad kontrollpanel använder du kontrollpanelens webbläsare. Bläddra till den instrumentpanel du vill använda i Dashboard Browser och markera den så att instrumentpanelens information visas. Markera på den högra panelen med information under **[!UICONTROL Operations]** avsnittet **[!UICONTROL Export Data]**.

Exporten initieras på servern och en exportindikator läggs till på **[!UICONTROL Exports]** menyn.

## Hämtar export {#section-0f03c5321c804867b7c72cf92f6f67d0}

När exporten är klar visas ett popup-meddelande om att exporten är klar.

![](assets/export_ready.png)

Använd **[!UICONTROL Exports]** menyn för att hämta exporten. Om du klickar på den gröna bockmarkeringen till höger om alternativet för den önskade exporten visas en listruta. På den här menyn väljer du under **[!UICONTROL Save Export As…]** undermenyn lämpligt menyalternativ för att hämta exporten i antingen CSV- eller Excel-format.

![](assets/export_save_as.png)

Filnedladdningen i webbläsaren startas nu.

Exporterna tas inte bort automatiskt, så du kan enkelt hämta exporten i varje format. Du kan ta bort exporter från **[!UICONTROL Exports]** menyn i den vänstra navigeringspanelen. Annars tas de bort automatiskt när du loggar ut.

Om du vill ta bort en export från **[!UICONTROL Export List]** dialogrutan klickar du på bockmarkeringen till höger om exporttiteln och väljer **[!UICONTROL Remove From List]**.

![](assets/export_remove_from_list.png)

