---
description: Med Insight Server (InsightServer64.exe) kan du definiera anpassade dimensioner från händelsedata eller sökdata.
title: Om utökade Dimensioner
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---

# Om utökade Dimensioner{#about-extended-dimensions}

Med Insight Server (InsightServer64.exe) kan du definiera anpassade dimensioner från händelsedata eller sökdata.

Alla anpassade dimensioner som du definierar kallas för utökade dimensioner. Ni kan använda dem för att skapa visualiseringar, bygga upp utökade mätvärden eller utföra analyser för att förstå de åtgärder och problem som är kopplade till er affärskanal. Du kan definiera flera typer av utökade dimensioner i [!DNL Transformation.cfg]-filen eller i [!DNL Transformation Dataset Include]-filer.

En utökad dimension representerar en relation mellan loggfältsvärden och en överordnad dimension. En överordnad dimension kan vara vilken användardefinierad räkningsbar dimension som helst. Se [Räknbara Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Du anger det överordnade objektet när du definierar dimensionen i [!DNL Transformation.cfg]-filen eller en [!DNL Transformation Dataset Include]-fil. En dimensions överordnade är samma som dess nivå. Om du till exempel definierar en dimension med en överordnad till Session, är den dimensionen en dimension på sessionsnivå.

>[!NOTE]
>
>Loggfältets värden kan komma från de interna värden som är tillgängliga i loggfilerna ( [!DNL .vsl]) eller andra händelseradatakällor eller från utökade loggfält som skapats med hjälp av omformningar.

Om du vill lägga till en utökad dimension i en visualisering öppnar du den från listan Utökat på [!DNL Select Dimension]-menyn. Om du till exempel vill lägga till en utökad dimension i en diagramvisualisering högerklickar du på arbetsytan och klickar på **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Om du vill ordna listan över de utökade dimensionerna i gränssnittet för dataläsaren kan du flytta de utökade dimensionerna till undermappar som du skapar. Se kapitlet Administrativa gränssnitt i *Datans Workbench användarhandbok*. Om du gör det visas undermapparnas namn också på menyn, som i Lägg till visualisering > Diagram > Utökat > &lt;*undermappsnamn*> > &lt;*dimensionsnamn*>.

Om du vill visa alla dimensioner som har definierats för datauppsättningsprofilen och buffertstorleken för varje, öppnar du gränssnittet [!DNL Detailed Status] i data workbench och klickar på **[!UICONTROL Performance]** och sedan **[!UICONTROL Dimensions]** för att expandera noderna. Buffertstorleken, som styr frågetiderna, anges i MB. Mer information om gränssnittet [!DNL Detailed Status] finns i handboken Server Administration and Installation.
