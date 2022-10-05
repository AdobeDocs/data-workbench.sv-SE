---
description: Maskering avser att markera en delmängd av dina data eller en delmängd av elementen i en dimension.
title: Maskera data
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 0%

---

# Maskera data{#mask-data}

{{eol}}

Maskering avser att markera en delmängd av dina data eller en delmängd av elementen i en dimension.

Du maskerar eller döljer de element som du inte vill ta med i analysen.

Data Workbench innehåller två metoder för att maskera dimensionselement. Den första metoden använder de alternativ som finns i [!DNL Mask] -menyn. Använda [!DNL Mask] kan du använda musen för att markera de element som ska visas eller maskeras, eller så kan du visa element på den översta nivån när du sorterar data efter mätvärden. Den andra metoden för att maskera dimensionselement använder en sökning.

**Maskera data**

1. Högerklicka på ett element eller etiketten för önskad dimension och klicka på **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Klicka på något av följande alternativ:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]**, eller **[!UICONTROL 500]** av de visade elementen sorterade efter mätvärden
   * **[!UICONTROL Show top > All Positive]** om du bara vill visa värden som är större än noll (0)
   * **[!UICONTROL Display “X more”]** för att visa antalet maskerade element
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*(endast tillgängligt när du arbetar med en normal dimension)

      När du arbetar med en normal dimension kan du med det här alternativet maskera en dimension med en räkningsbar dimension. När du väljer det här alternativet visas endast de element som har minst ett element av den räkningsbara dimensionen som du har valt. Tabellen visar upp till 1 023 element.

>[!NOTE]
>
>På grund av Adobe [!DNL Platform] bearbetar data i slumpmässig ordning, och när minst en maskering resulterar i mer än 1 023 element, har de vanligaste och större elementen större chans att inkluderas i tabellen.

När du maskerar med Visa överkant eller Minst en, motsvarar ordningen i tabellen som standard de värden som påverkas av markeringen vid den tidpunkten. Om du senare ändrar markeringen ändras inte ordningen från den ursprungliga ordningen om inte tabellen sorteras om eller du aktiverar Dynamisk markering. När du klickar **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, sorteras tabellen om varje gång du ändrar markeringen.

**Maskera data med hjälp av en sökning**

* Du kan maskera data med något av följande sökalternativ:

   * Högerklicka på ett element eller etiketten för önskad dimension och klicka på **[!UICONTROL Mask]** och sedan i [!DNL Search] anger du den fras du vill söka efter.

      ![](assets/mnu_Table_MaskSearch.png)

   * Högerklicka på ett element eller etiketten för önskad dimension och klicka på **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]** och skriv sedan den fras du vill söka efter i sökrutan som visas i måttetikettcellen.

      ![](assets/vis_Table_Mask_searchBar.png)

      När du skriver in en sökfras uppdateras Datan Workbench så att matchningarna återspeglas.

Om du vill begränsa maskningen ytterligare under en sökning kan du använda någon av följande metoder:

* Du kan skriva &quot;re:&quot; i [!DNL search] om du vill att sökfrasen ska tolkas som ett reguljärt uttryck. Du kan använda vilken syntax som helst som är kopplad till reguljära uttryck i sökfrasen. Mer information om reguljära uttryck finns i bilagan Reguljärt uttryck i dialogrutan *Konfigurationshandbok för datauppsättning*.
* Du kan skriva $-symbolen som det första tecknet i söksträngen för att hitta fraser som börjar med strängen du angav, eller som det sista tecknet för att hitta fraser som slutar med strängen du angav.
* Du kan skriva ett mellanslag som det första tecknet i söksträngen för att hitta ord i en fras som börjar med strängen du angav, eller som det sista tecknet för att hitta ord i en fras som slutar med strängen du angav.

Här följer exempel på olika sätt att maskera en tabell med strängen &quot;on&quot; i en sökning:

* När du skriver &quot;on&quot; visas alla fraser som innehåller strängen &quot;on&quot; var som helst i frasen: &quot;**på** linbanktjänster&quot;&quot;c **på** takköpare&quot;,&quot;bulli **på** mynt, **på** rad,&quot;&quot;guldopti **på** s,&quot; och&quot;silverbulli **på**.&quot;
* Om du skriver &quot;$on&quot; visas alla fraser som börjar med strängen &quot;on&quot;:

   &quot;**på** linbanktjänster och &quot;**på**-line-betalning.&quot;

* Om du skriver &quot;on$&quot; visas alla fraser som slutar med strängen &quot;on&quot;:

   &quot;silverbulli **på**&quot; och &quot;guldopti **på**.&quot;

* Om du skriver &quot;on&quot; visas alla fraser som innehåller ett ord som börjar med strängen &quot;on&quot;:

   &quot;**på** bankverksamhet och bankverksamhet **på** line.&quot;

* Om du skriver &quot;on&quot; visas alla fraser som innehåller ett ord som slutar med strängen &quot;on&quot;:

   &quot;bulli **på** mynt och &quot;silverbulli&quot;**på**.&quot;

* Om du använder &quot;on&quot; visas alla fraser som innehåller strängen &quot;on&quot; som ett ord:

   &quot;**på** bankverksamhet och bankverksamhet **på** line.&quot;
