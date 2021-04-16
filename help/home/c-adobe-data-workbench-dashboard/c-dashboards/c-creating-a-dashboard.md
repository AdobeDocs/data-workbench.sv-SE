---
description: Vi rekommenderar att du skapar en kontrollpanel även för kortsiktiga, ad hoc-analyser.
title: Skapa en kontrollpanel
uuid: 5b9e9db2-d7ac-4c97-8df0-74a9e5a0c496
exl-id: bd51d4c0-bcf2-4ba6-8b32-de06c74f359f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Skapa en instrumentpanel{#creating-a-dashboard}

Vi rekommenderar att du skapar en kontrollpanel även för kortsiktiga, ad hoc-analyser.

>[!NOTE]
>
>Skrivskyddade användare kan inte skapa instrumentpaneler. Det här avsnittet gäller endast vanliga användare och administratörer.

Användarna kan välja att skapa kontrollpaneler av flera olika anledningar:

* En ny instrumentpanel kan startas från början för direktanalys utan avsikt att återanvända eller dela instrumentpanelen.
* En ny kontrollpanel kan skapas för att du ska kunna utföra en egen personlig analys som du vill spara och återanvända, men inte dela.
* En ny kontrollpanel kan skapas, sparas och delas av dig och resten av kontrollpanelens användarpopulation. Oavsett hur det är så börjar varje scenario på samma plats: en tom arbetsyta för kontrollpanelen.

>[!NOTE]
>
>Innan du börjar bygga ut kontrollpanelen kan det vara bra att minska procentandelen för frågan till något lågt, till exempel 10 eller 25 procent. Detta kommer att hämta dataprover från Data Workbench mycket snabbare än att utföra en fullständig fråga. Eftersom dessa samplingsresultat returnerar mycket snabbare ger det idealisk svarstid när du utformar instrumentpanelen och analyserna. När du är klar att köra frågor som ska slutföras kan du uppdatera parametern query-to till 100 procent. Information om hur du justerar frågeslutförandet finns i [Fråga till parameter](../../../home/c-adobe-data-workbench-dashboard/c-dashboards/c-query-to-parameter.md#concept-33db106e28bc4108bca9e8d0a440d323).

Om du vill skapa en ny kontrollpanel väljer du **[!UICONTROL New]** på kontrollpanelens meny.

![](assets/new_dashboard.png)

Du kommer att få en tom kontrollpanel där visualiseringar kan läggas till och konfigureras baserat på dina analysbehov. När du arbetar uppdateras ingenting på servern förrän du sparar.

Bestäm sedan vilken typ av data du vill visa och hur du vill visa den. Det är vanligtvis till att börja med tabellvisualiseringar för att se rådata och sedan bygga ut andra diagram efter behov. Mer information om hur du lägger till och konfigurerar visualiseringar finns i [Skapa visualiseringar](../../../home/c-adobe-data-workbench-dashboard/c-visualizations/t-creating-visualizations.md#task-c6f1d20fa2484aeeb9a8487625054ecf). När du har lagt till och konfigurerat visualiseringar för att bygga ut kontrollpanelen får du följande:

![](assets/after_configure.png)

Från och med nu kan du utföra analysen och ta bort instrumentpanelen eller välja att spara instrumentpanelen på servern för återanvändning och/eller delning. Information om hur du interagerar med en kontrollpanel för att utföra analys finns i avsnittet [Göra markeringar på kontrollpanelen](../../../home/c-adobe-data-workbench-dashboard/c-making-selections-within-the-dashboard/c-making-selections-within-the-dashboard.md#concept-0989862de0044cc4bbfd7f4441275fc4).
