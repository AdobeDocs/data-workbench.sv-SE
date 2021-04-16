---
description: Följ de här stegen för att använda visualiseringen av förmånsbedömning.
title: Ställa in benägenhetsbedömning
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
exl-id: e16a7062-636e-44a9-a07d-343d48bf1b4c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Ställa in benägenhetsbedömning{#setting-up-propensity-scoring}

Följ de här stegen för att använda visualiseringen av förmånsbedömning.

1. Öppna en ny arbetsyta och klicka på **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. Ange **[!UICONTROL Target]** (den beroende variabeln).

   Ange den beroende variabeln genom att markera:

* **Dimension-element**: Högerklicka på arbetsytan och välj  **[!UICONTROL Table]**. Markera sedan ett element i Dimensionen som din beroende variabel.

   ELLER

* **[!UICONTROL Filter Editor]**. Klicka på **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** för att öppna filterredigerarens visualisering.

   ![](assets/propensity_visualization_filter_editor.png)

   När du har markerat ett element i Dimensionen eller ett filter som den beroende variabeln klickar du på **[!UICONTROL Set Target]** och anger ett namn som beskriver den beroende variabeln. Klicka sedan på **[!UICONTROL OK]** (och se till att filterrutan är markerad) för att ställa in målet.

   ![](assets/propensity_visualization_setTarget.png)

   Namnet som du ger målet är den beroende variabeln som visas i den vänstra rutan.
1. Lägg till oberoende variabler.

   Lägg till de oberoende variablerna med Metrisk eller Dimension Elements.

   ![](assets/propensity_visualization_metrics.png)

* **Mätvärden**. Välj ett mätvärde på menyn **[!UICONTROL Metrics]** i verktygsfältet Propensitetsbedömning.

* **Dimension-element**: Högerklicka på arbetsytan och välj  **[!UICONTROL Table]**. Markera ett eller flera textelement och dra till den vänstra Dimensionen under **[!UICONTROL Independent Variables]** eller till rutan **[!UICONTROL Element]** med hjälp av tangenterna `<Ctrl>` + `<Alt>`.

1. Ange **[!UICONTROL Training Filter]**. Du kan definiera den uppsättning besökare som du vill poängsätta genom att klicka på **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** i verktygsfältet Propensitetsbedömning. Detta ger en delmängd av data som byggts med enbart de besökare som du vill poängsätta. Exempel: besökare som besökt den senaste månaden, besökare som bor i Australien eller besökare som har tittat på specifika produkter.

   Standardfiltret är **[!UICONTROL Train on Everyone]**, men du kan ändra det genom att aktivera **[!UICONTROL Dimension Elements]** i en tabell eller skapa ett filter med **[!UICONTROL Filter Editor]**.

   När du har markerat ett filterelement eller skapat ett filter och aktiverat klickar du på **Alternativ** > **Ange utbildningsfilter**, anger ett namn som beskriver Dimensionen och klickar sedan på **[!UICONTROL OK]**.
1. När du har identifierat alla indata trycker du på **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   Bedömningsprocessen börjar med att skicka data flera gånger. Resultatet visas sedan som stapeldiagram över en procentlinje.
1. Spara benägenhetspoäng.

   Från och med 6.1 har du nu ett alternativ när du använder Spara benägenhetspoäng:

* Dimension
* Dimension och mått

   Du kan få två sparade filer, både en dimension och ett definierat mått.

   >[!NOTE]
   >
   >Om du skickar Propensity Score för bearbetning får du bara en dimension.

   Det härledda måttet är det associerade medelpoängsmåttet.
1. Kontrollera noggrannheten.

   Systemet visar **[!UICONTROL Model Complete]** och genererar en poängmodell när processen är klar.

   Högerklicka på **[!UICONTROL Model Complete]** för att identifiera noggrannheten för bedömningsmodellen enligt definitionen i systemet. Värden från 0 procent till 100 procent identifierar sannolikheten för att besökarna matchar variabeln **[!UICONTROL Target]**.

   Sammanfusionsmatrisen ger fyra tal genom kombinationen av Faktiskt positivt (AP), Faktiskt negativt (AN), Förutsagt positivt (PP) och Förutsagt negativt (PN). Dessa siffror erhålls genom att använda den resulterande poängmodellen på de 20 %-testdata som vi vet det sanna svaret på. Om poängen är större än 50 % förutspås det som ett positivt fall (matcha den definierade händelsen).

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> Noggrannhet</b> </td> 
   <td colname="col2"> Anger hur korrekt modellen är genom att identifiera rätt prognoser för alla prognoser. <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Återkalla</b> </td> 
   <td colname="col2"> Identifierar möjligheten att återidentifiera poängmodellen. <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> Precision</b> </td> 
   <td colname="col2">Identifierar graden av diskrepans. <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Öppna ett [Lyft- eller magasin-schema](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a) eller [modellvisningsprogram](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   Högerklicka på visualiseringen **Modellen är klar** och välj **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]** eller **[!UICONTROL Model Viewer.]**
