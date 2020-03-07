---
description: Välj indatavariabler, antalet kluster och en målpopulation (om du vill) för att definiera kluster i datauppsättningen.
solution: Analytics
title: Byggkluster
topic: Data workbench
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Byggkluster{#building-clusters}

Välj indatavariabler, antalet kluster och en målpopulation (om du vill) för att definiera kluster i datauppsättningen.

**Byggkluster**

1. Öppna **[!UICONTROL Cluster Builder]**.

   Klicka på **Visualisering** > **Predictive Analytics** > **Clustering** > **Cluster Builder**.

   ![](assets/cluster-builder-step1.png)

1. Välj indatavariabler.

   * Lägg till mätvärden i **[!UICONTROL Input Variables]** listan genom att välja på **[!UICONTROL Metric]** menyn i verktygsfältet.

      ![](assets/cluster_metric_select.png)

   * Lägg till dimensionselement i **[!UICONTROL Input Variables]** listan genom att dra dem från en dimensions tabell.

      Tryck på **[!UICONTROL Ctrl + Alt]** och dra de markerade dimensionselementen till **[!UICONTROL Input Variables]** listan eller till **[!UICONTROL Element]** rutan i verktygsfältet.

      ![](assets/cluster_dim_select.png)
   Som standard utförs klustring på hela datauppsättningen. Du kan se alla indatavariabler i den vänstra **[!UICONTROL Preprocessing]** rutan.
1. Använd menyn **[!UICONTROL Options]** för att välja önskat antal kluster.

   ![](assets/build_cluster_2.png)

1. Om du vill gruppera en deluppsättning av besökarna i datauppsättningen kan du definiera ett populationsfilter.

   ![](assets/build_cluster_3.png)

   Börja med att definiera önskad delmängd med hjälp av markeringar på arbetsytan eller med hjälp av **[!UICONTROL Filter Editor]**. När du har markerat önskad delmängd anger du målpopulationen på **[!UICONTROL Options]** menyn. Vi rekommenderar att du ger målgruppen ett ID-namn.

   Menyn innehåller även inställningar som styr det maximala antalet omgångar och det godtagbara tröskelvärdet för centrerad konvergens. **[!UICONTROL Options]**

1. När indata och alternativ har konfigurerats klickar du på knappen **Gå** för att köra klustringen lokalt eller på **[!UICONTROL Submit]** för att skicka uppgiften till Predictive Analytics Server. Inskickat material till servern sparar den resulterande dimensionen i datauppsättningen när konverteringen är klar.

   När du kör lokalt ser du hur Klusterbyggaren rör sig genom fyra klustringssteg för canopy när den definierar intelligenta center baserat på indata.

   När klustrets mittpunkter inte ändras mer än det angivna konverteringströskelvärdet, konverteras klusterdimensionen och i Klusterbyggaren visas ytterligare information om hur relevant en inmatning var för varje kluster.

1. Anpassa klustren.

   Om du högerklickar på statistikens färgfält öppnas en snabbmeny där du kan anpassa tröskelvärdena för relevans och, när det gäller dimensionselementets fördelning, välja vilket test som ska visas.

   ![](assets/build_cluster_7.png)

   Mätvärden ger ett t-test för varje kluster, medan indata för dimensionselement ger tre distributionstester (Chi-kvadrat, en U-entropi och Cramers V-statistik) för varje kluster.

   >[!NOTE]
   >
   >Om du lägger till eller tar bort indata under konverteringen pausas processen tills du trycker på **Gå** igen.

   När du har skapat kluster kan du öppna färgväljaren och tilldela färger för olika distributionsresultat.

   ![](assets/build_cluster_5.png)

1. När klusterdimensionen är konverterad kan du lägga till mått i tabellen och göra markeringar som vanligt. Du kan också högerklicka på elementnamnen (Klustera 1, Klustera 2 osv.) för att öppna snabbmenyn och ge dem ett mer meningsfullt namn.

   ![](assets/build_cluster_6.png)

1. Om du vill använda den här klusterdimensionen i andra visualiseringar kan du göra **[!UICONTROL Save]** det lokalt eller **[!UICONTROL Submit]** det till servern.

Om du vill köra konvergens igen eller se relevansen för indata kan Klusterbyggaren även läsa in befintliga klusterdimensioner.

>[!TIP]
>
>När det här alternativet är markerat kommer alla indatavariabler att frisläppas och du får en tom klusterbyggarvisualisering för att definiera nya kluster. **[!UICONTROL Reset]**

