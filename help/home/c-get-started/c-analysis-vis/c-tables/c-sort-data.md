---
description: Steg för att sortera data.
solution: Analytics
title: Sortera data i en tabell
topic: Data workbench
uuid: 66869478-922d-41e1-915d-3ed7bff3b08d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sortera data i en tabell{#sort-data-in-a-table}

Steg för att sortera data.

Om tabellen bara har en dimension kan du klicka på etiketten för det mätvärde som du vill sortera data på.

1. Högerklicka på ett element eller etiketten för dimensionen som du vill sortera och klicka sedan på **[!UICONTROL Sort]**.

   ![](assets/mnu_Table_Sort.png)

1. Klicka på något av följande alternativ:

   * **[!UICONTROL By ordinal]** för att sortera elementen efter elementens naturliga ordning. Elementen i timdimensionen visas i kronologisk ordning. Om dimensionen inte har någon naturlig ordning, t.ex. med referens eller URI, är sorteringsordningen inte användbar, så du bör välja att sortera antingen alfabetiskt eller efter mått.
   * **[!UICONTROL Alphabetically]** om du vill sortera dimensionen i bokstavsordning efter elementnamn.
   * **[!UICONTROL By metric]** för att välja ett mått som du vill sortera data efter. Du kan till exempel sortera referensdimensionen efter sessionsmåtten för att se vilka referenter som bidrar mest till sessionerna på din webbplats.

      När du sorterar efter ett mätvärde motsvarar ordningen i tabellen som standard värdena i måttet som påverkas av markeringen vid den tidpunkten. Om du senare ändrar markeringen ändras inte sorteringsordningen från den ursprungliga ordningen, såvida inte dimensionen sorteras om eller du aktiverar Dynamisk markering. När du klickar **[!UICONTROL Sort]** > **[!UICONTROL Dynamic Selection]** sorteras tabellen om varje gång du ändrar markeringen.
   Om du vill sortera efter ett befintligt mått i tabellen klickar du på måttetiketten.

1. (Valfritt) Om du vill välja om du vill sortera i stigande eller fallande ordning högerklickar du på ett element eller etiketten för dimensionen som du vill sortera och klickar sedan på **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Ascending]** eller **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Descending]**.

   Om tabellen bara har en dimension kan du klicka på måttets etikett för att vända sorteringsordningen. Om du klickar på etiketten igen inverteras sorteringsordningen.

