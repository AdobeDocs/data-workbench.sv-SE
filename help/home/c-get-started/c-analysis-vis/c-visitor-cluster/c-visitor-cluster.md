---
description: Med besöksklustring kan ni utnyttja kundegenskaper för att dynamiskt kategorisera besökare och generera klusteruppsättningar baserat på valda dataindata, vilket identifierar grupper som har liknande intressen och beteenden för kundanalys och målgruppsanpassning.
title: Besökskluster
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
exl-id: 68c1845d-9c49-4ad9-adf3-c123d08cf758
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 1%

---

# Besökskluster{#visitor-clustering}

Med besöksklustring kan ni utnyttja kundegenskaper för att dynamiskt kategorisera besökare och generera klusteruppsättningar baserat på valda dataindata, vilket identifierar grupper som har liknande intressen och beteenden för kundanalys och målgruppsanpassning.

**Klustringsprocess**

Klusterprocessen kräver att du identifierar mått och dimensionselement som ska användas som indata, och gör det möjligt att välja en specifik målpopulation för att använda dessa element för att skapa angivna kluster. När du kör klusterprocessen använder systemet mått- och dimensionsindata för att fastställa lämpliga startcenter för det angivna antalet kluster. Dessa center används sedan som utgångspunkt för att tillämpa algoritmen K-Means.

![](assets/K_algorithm.png)

* De första centrumen väljs på ett intelligent sätt via ett Canopy Clustering-pass.
* Datakluster skapas genom att varje datapunkt kopplas till närmaste center.
* Medelvärdet för var och en av K-klustren blir det nya centrumet.
* Algoritmen upprepas i steg 2 och 3 tills konvergens uppnås. Detta kan ta flera omgångar.

Med **[!UICONTROL Maximum Iterations]** på **[!UICONTROL Options]**-menyn kan analytikern ange det maximala antalet iterationer som ska utföras av klusteralgoritmen. Om du anger det här alternativet kan det leda till att klusterprocessen slutförs snabbare, baserat på den maximala iterationshastigheten, på bekostnad av exakt konvergens för klustercentren.

>[!NOTE]
>
>När du har definierat kluster kan du spara Dimensionen för kluster och använda dem precis som andra dimensioner. Den kan också läsas in i klusterutforskaren för att undersöka separationen av klustercenter.

I Klusterbyggaren kan du välja **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** för att välja algoritmer när du definierar kluster. För närvarande finns det tre algoritmer som stöds:

* KMeans
* Kmeans`++`
* Förväntningsmaximering

Det finns två sätt att köra klusterprocessen:

* Metod 1 - Klicka på **[!UICONTROL Go]** i klustervisualiseringsfönstret.
* Metod 2 - Klicka på **[!UICONTROL Submit]** i klustervisualiseringsfönstret, som skickar klusterjobbet direkt till servern. Du kan spåra förloppet med alternativet &quot;Detaljerad status för fråga&quot;.

![](assets/dwb_visitorclustering.png)

Algoritmen har följande begränsningar:

1. Om du använder metod 1 kan du välja någon av de klusteralgoritmer som stöds.
1. Om du använder metod 2 kan du välja keying eller kmeans++. Alternativet Förväntningsmaximering är inte tillgängligt.

>[!NOTE]
>
>I filen [!DNL DPU.cfg] är värdet för Fråga, minnesgräns som standard 500 MB. Värdet måste ökas när flera klusterjobb körs. Om du till exempel kör 5 klusterjobb parallellt ökar du värdet till 1 GB. Det finns inget sätt att avbryta klusterjobbet utan att starta om servern.

**Rekommendationer**

Antalet iterationer (antal gånger som data skannas) och det konverteringströskelvärde som du konfigurerar påverkar klustringens prestanda negativt. Följande tabell innehåller en bredare riktlinje som du kan följa:

| Antal kluster | Algoritm | Iterationer | Konvergenströskel | Normalisering |
|---|---|---|---|---|
| 6 | Kmeans | 25,50 | 1e-3 | Min-Max |
| 6 | Kmeans | 25,50 | 1e-6 | Min-Max |
| 6 | Kmeans++ | 50 | 1e-6 | Min-Max |
