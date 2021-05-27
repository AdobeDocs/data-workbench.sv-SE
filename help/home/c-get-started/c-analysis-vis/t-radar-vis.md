---
description: Radardiagram ger snabb fokusering på de områden som behöver uppmärksammas mest genom att ge en visuell bild av en uppsättning mätvärden och hur de relaterar eller skiljer sig.
title: Radarvisualisering
uuid: 39d67743-b6c1-46f1-99fd-7c71dfe07932
exl-id: 5385d903-422b-4936-bbb3-0d5ee4d286de
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---

# Radarvisualisering{#radar-visualization}

Radardiagram ger snabb fokusering på de områden som behöver uppmärksammas mest genom att ge en visuell bild av en uppsättning mätvärden och hur de relaterar eller skiljer sig.

Många gånger behöver du mer än ett mått för att förstå och utvärdera valda observationer på en arbetsyta.

Den här visualiseringen är användbar för jämförelser eller riktmärken mellan tabellvalen. Du kan t.ex. lägga till en arbetsytetabell som listar butiker och sedan lägga till en radarvisualisering med mätvärden som Intäkter, Besökare och Sidvyer. (Som visas på skärmen i följande procedur.) När du gör butiksmarkeringar i tabellen flyttas radardiagrammets fotavtryck, vilket identifierar svagheter eller styrkor i måtten för den valda butiken.

Varje radial i ett radardiagram är ett mått och minst tre mätvärden krävs. Måttdata ritas i relation till ett förankrat mått. Det förankrade måttet och parametern Skala till ankarpunkt för varje mätvärde avgör måttets skalning i förhållande till riktmärkena.

**Skapa en radarvisualisering**

1. Högerklicka i arbetsytan och klicka sedan på **[!UICONTROL Visualization]** > **[!UICONTROL Radar]**.

   ![](assets/client-rad.png)

1. Om du vill lägga till mått högerklickar du i visualiseringen och väljer **[!UICONTROL Add Metric]**.
1. Om du vill förankra ett mätresultat i diagrammet högerklickar du på ett mätresultat och väljer följande alternativ:

   **Fäst mot det här måttet:** Använder det här måttet som riktmärke som andra mätvärden ritas till. Du kan förankra ett mått i taget. Varje mätvärde i diagrammet filtreras efter den aktiva arbetsytan eller efter inget filter. Riktvärdesförhållandet mellan dessa två värden ritas på axeln mellan diagrammets mitt och metriskt namn på radarn. Noll ritas i mitten.

1. Om du vill skalförändra ett mått med det förankrade måttet högerklickar du på måttet och väljer följande alternativ:

   **Skala med ankarpunkt:** När det här måttets axel är aktiverat skalas den så att referensförhållandet för det valda ankarpunktsmåttet ritas i cirkeln, med noll i mitten. När cirkeln inte är vald representerar den ett referensvärde på 1. Vanligtvis aktiverar du Skala med ankarpunkt för räkningsbara mått, som besökare eller sidvyer, och inaktiverar det för proportionsmått som Konvertering, Genomsnittlig sessionstid eller Sidvyer per session.
