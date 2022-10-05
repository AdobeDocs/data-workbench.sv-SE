---
description: Välj indatavariabler, antalet kluster och en målpopulation (om du vill) för att definiera kluster i datauppsättningen.
title: Byggkluster
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---

# Byggkluster{#building-clusters}

{{eol}}

Välj indatavariabler, antalet kluster och en målpopulation (om du vill) för att definiera kluster i datauppsättningen.

**Byggkluster**

1. Öppna **[!UICONTROL Cluster Builder]**.

   Klicka **Visualisering** > **Prediktiv analys** > **Klustring** > **Cluster Builder**.

   ![](assets/cluster-builder-step1.png)

1. Välj indatavariabler.

   * Lägg till mätvärden i **[!UICONTROL Input Variables]** genom att välja i **[!UICONTROL Metric]** i verktygsfältet.

      ![](assets/cluster_metric_select.png)

   * Lägg till dimensionselement i **[!UICONTROL Input Variables]** genom att dra dem från en Dimensions tabell.

      Tryck **[!UICONTROL Ctrl + Alt]** och dra markerade dimensionselement till **[!UICONTROL Input Variables]** eller till **[!UICONTROL Element]** i verktygsfältet.

      ![](assets/cluster_dim_select.png)
   Som standard utförs klustring på hela datauppsättningen. Du kan se alla indatavariabler till vänster **[!UICONTROL Preprocessing]** fönster.
1. Använd **[!UICONTROL Options]** för att välja önskat antal kluster.

   ![](assets/build_cluster_2.png)

1. Om du vill gruppera en deluppsättning av besökarna i datauppsättningen kan du definiera ett populationsfilter.

   ![](assets/build_cluster_3.png)

   Börja med att definiera önskad delmängd med hjälp av markeringar på arbetsytan eller med hjälp av **[!UICONTROL Filter Editor]**. När du har markerat önskad delmängd anger du målpopulationen i dialogrutan **[!UICONTROL Options]** -menyn. Vi rekommenderar att du ger målgruppen ett ID-namn.

   The **[!UICONTROL Options]** -menyn har även inställningar som styr det maximala antalet omgångar och det godtagbara tröskelvärdet för centrerad konvergens.

1. När indata och alternativ har konfigurerats klickar du på **Gå** om du vill köra klustret lokalt eller trycka på **[!UICONTROL Submit]** för att skicka uppgiften till Predictive Analytics Server. Inskickat material till servern sparar den resulterande dimensionen i datauppsättningen när konverteringen är klar.

   När du kör lokalt ser du hur Klusterbyggaren rör sig genom fyra klustringssteg för canopy när den definierar intelligenta center baserat på indata.

   När klustrets mittpunkter inte ändras mer än det angivna konverteringströskelvärdet konverteras Dimensionen Cluster och Klusterbyggaren visar ytterligare information om hur relevant en inmatning var för varje kluster.

1. Anpassa klustren.

   Om du högerklickar på statistikens färgfält öppnas en snabbmeny där du kan anpassa tröskelvärdena för relevans och, när det gäller dimensionselementets fördelning, välja vilket test som ska visas.

   ![](assets/build_cluster_7.png)

   Mätvärden ger ett t-test för varje kluster, medan indata för dimensionselement ger tre distributionstester (Chi-kvadrat, en U-entropi och Cramers V-statistik) för varje kluster.

   >[!NOTE]
   >
   >Om du lägger till eller tar bort indata under konverteringen pausas processen tills du trycker på **Gå** igen.

   När du har skapat kluster kan du öppna färgväljaren och tilldela färger för olika distributionsresultat.

   ![](assets/build_cluster_5.png)

1. Med Dimensionen Kluster konverterad kan du lägga till mått i tabellen och göra markeringar som vanligt. Du kan också högerklicka på elementnamnen (Klustera 1, Klustera 2 osv.) för att öppna snabbmenyn och ge dem ett mer meningsfullt namn.

   ![](assets/build_cluster_6.png)

1. Om du vill använda den här klusterdimensionen i andra visualiseringar kan du **[!UICONTROL Save]** lokalt eller **[!UICONTROL Submit]** till servern.

Om du vill köra konvergens igen eller se relevansen för indata kan Klusterbyggaren även läsa in befintliga klusterdimensioner.

>[!TIP]
>
>När du har valt **[!UICONTROL Reset]** kommer att släppa alla indatavariabler fullständigt och ge dig en tom klusterbyggarvisualisering för att definiera nya kluster.
