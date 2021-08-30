---
description: Använd guiden Metrisk nedtoning för att skapa en ny Dimension.
title: Guiden Metrisk dim
uuid: 77b9bc8e-7625-4fef-9de4-f113f9b2debd
exl-id: 109fbefc-5608-493d-aec9-8337f21eaa70
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---

# Guiden Metrisk dim{#metric-dim-wizard}

Använd guiden Metrisk nedtoning för att skapa en ny Dimension.

Med en metrisk toning omvandlas ett mått till en ny dimension. Om du t.ex. använder en måttenhet som bygger på måtten för sidvyer och nivån för besökare visas dimensionselement baserat på den totala sidvyn för varje besökare. Med den kan du utöka ett definierat mått baserat på dimensionselement för att skapa och spara som en ny dimension.

## Steg 1: välj dimension och mått {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. **Öppna guiden** Metrisk dim.

   Högerklicka på en arbetsyta och välj **Verktyg** > **Skapa metrisk dim**.

1. **Ange namnet Metrisk dim**.

   Som standard fylls namnfältet i automatiskt baserat på nivå- och måttval.

1. **Markera en Dimension.** Dimensionsnivån är den överordnade dimensionen som innehåller alla ingående elementvärden för att filtrera indata och definiera en dimensionstyp.

   Dimensionerna är följande:

   * Klickande
   * Träff
   * Produkt
   * Gå in på
   * Besökare

1. **Välj ett mått**.

   Välj ett fördefinierat mått som ska utökas och sparas som en måttenhet.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (valfritt) **Skapa en måttformel**.

   Klicka i rutan för att ange en anpassad måttformel. Det beräknade förhandsgranskningsvärdet visas när uttrycket valideras.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Du kan lägga till ett eget [måttuttryck](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) eller klippa ut och klistra in från en annan måttredigerare eller visualisering. Syntaxfel, formelfel, odefinierade filter och andra fel rapporteras i guiden.

1. Klicka på **Nästa**.

## Steg 2: formatera och ange bucklar {#section-5bddf3cd306545d7806a501637f80f77}

Du kan välja måttformat och ange bucketvärden för ett dimensionsuttryck.

1. Välj **Format** för den nya måttdim.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Formatet definierar hur måttet presenteras när det öppnas i en visualisering. Dessa format är valda [utskriftsstandarder](http://www.cplusplus.com/reference/cstdio/printf/), som definieras nedan:

   ```
   %[flags][width][.precision][length][specifier]
   %
   0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   I fältet **Förhandsgranska** visas ett värde baserat på det valda måttet och formatet.

1. Lägg till uttrycket **Antal buffertar**.

   Du kan definiera en måtttoning med olika intervall, eller intervall. Detta returnerar delmängder av element baserat på storlek, t.ex. [0-4], [5-10],..). Elementen på Dimensionen Nivå relaterar till de element vars intervall innehåller måttvärdet. Se beskrivningen av bucket-uttrycket på [Syntax for Dimension Expressions](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Klicka på **Förhandsgranska** om du vill öppna tabellen med värden för Metrisk Dim innan du sparar.

   ![](assets/6_4_workstation_metricdim_preview.png)

   Registret innehåller mätvärden per metrisk dim.

1. Klicka på **Visa på Dimension-menyn** för att lägga till den nyligen skapade dimensionen på fliken **Dimension** i **Finder**.
1. Klicka på **Nästa**.

## Steg 3: avsluta och spara {#section-d9043235b18a425f9de0db668d4b1683}

1. Välj det här alternativet om du vill starta Metrisk toningsredigerare, diagramvisualisering eller tabell när du har sparat.

   | Fält | Beskrivning |
   |---|---|
   | Starta Metric Dim Editor | Öppna Metrisk toningsredigerare. |
   | Starta diagram | Starta en PNG-bild av tabellen. |
   | Starta tabell | Starta en tabell på arbetsytan med värden i kolumner som visar värden för den nya metriska dim-metoden jämfört med värdena för det valda måttet. |

1. Klicka på **Slutför** och spara.

   En dialogruta öppnas där du kan spara filen. De valda alternativen för att visa värden öppnas på arbetsytan.
