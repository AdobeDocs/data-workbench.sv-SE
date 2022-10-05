---
description: Klusterverktyget innehåller nu en KMeans++-algoritm (endast KMeans-algoritmen stöds tidigare) som använder en snabbare metod för att hitta center för en snabbare klustergenereringsprocess.
title: Klustring 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
exl-id: 6a779ddc-c8f1-4c55-9c17-1119fe1aa791
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Klustring 2.0{#clustering}

{{eol}}

Klusterverktyget innehåller nu en KMeans++-algoritm (endast KMeans-algoritmen stöds tidigare) som använder en snabbare metod för att hitta center för en snabbare klustergenereringsprocess.

## KMeans Algorithms {#section-92383a1be1d6402c95a25c902e90b850}

I [Cluster Builder](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html?lang=en)kan du nu välja **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** för att välja algoritmer när kluster definieras.

* **[!UICONTROL KMeans]**. Den här algoritmen använder canopy-klustring för att definiera klustrets mittpunkter.
* **[!UICONTROL KMeans++]**. Den här algoritmen underlättar klusteruppbyggnaden när den körs mot stora datauppsättningar.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ är en förbättrad implementering av KMeans-algoritmen eftersom den ger bättre initiering av inledande k-center. (Den ursprungliga KMeans-algoritmen väljer initiala mittpunkter slumpmässigt.) KMeans++ väljer det första centrumet slumpmässigt. De återstående k-1-centrumen väljs en i taget baserat på den sträcka en datapunkt är till närmaste befintliga centrum. De längst datapunkter har större chans att väljas som ett nytt center än närliggande datapunkter. När den inledande mittpunkten har valts utförs proceduren på exakt samma sätt som den ursprungliga KMeans-klustringen.

Arbetsflödet för KMeans++ är exakt detsamma som arbetsflödet för KMeans-klustring, förutom att du måste välja **Alternativ** > **Algoritm** > **KMeans++** i klusterverktyget.

>[!NOTE]
>
>Varje DPU kör sin egen KMeans++-procedur på sin egen datadel. Om DPU:n har tillräckligt med tillgängligt minne (förhållandet kan konfigureras i filen PAServer.cfg), kommer data för dessa berörda variabler att hämtas till minnet. De återstående K-1-initiala mittmarkeringarna och konvergeringsiterationerna sker alla i minnet, vilket är snabbare än den tidigare KMeans-klustringen.
