---
description: Skapa dimensioner som definieras av måttattribut (Mått) med en steg-för-steg-guide. Testa, förhandsgranska och spara sedan den nya måttenheten i Dimensions-listan.
title: Guiden Metrisk dim
uuid: 411b2e28-0958-43bb-a853-7de7b3063818
translation-type: tm+mt
source-git-commit: d892186621e7acb9504254496b038efc3e9fd8ec

---


# Guiden Metrisk dim{#metric-dim-wizard}

Skapa dimensioner som definieras av måttattribut (Mått) med en steg-för-steg-guide. Testa, förhandsgranska och spara sedan den nya måttenheten i Dimensions-listan.

Med en metrisk toning omvandlas ett mått till en ny dimension. Om du t.ex. använder en måttenhet som bygger på måtten för sidvyer och nivån för besökare visas dimensionselement baserat på den totala sidvyn för varje besökare. Med den kan du utöka ett definierat mått baserat på dimensionselement för att skapa och spara som en ny dimension.

## Steg 1: Välj dimension och mått {#section-58b6ea7bbba5487ba1a3c264aa3dcb95}

1. Öppna guiden Metrisk dim.

   Högerklicka på en arbetsyta och välj **[UICONTROL-verktyg]** > **[UICONTROL Skapa metrisk dim]**.

1. Ange namnet Metrisk dim.

   Som standard fylls namnfältet i automatiskt baserat på nivå- och måttval.

1. Välj en dimensionsnivå.

   Dimensionsnivån är den överordnade dimensionen som innehåller alla ingående elementvärden för att filtrera indata och definiera en dimensionstyp.

   Dimensionsnivåerna omfattar:

   * Klickande
   * Träff
   * Produkt
   * Besök
   * Besökare

1. Välj ett mått.

   Välj ett fördefinierat mått som ska utökas och sparas som en måttenhet.

   ![](assets/6_4_workstation_metricdim_metric.png)

1. (valfritt) Skapa en måttformel.

   Klicka i rutan för att ange en anpassad måttformel. Det beräknade förhandsgranskningsvärdet visas när uttrycket valideras.

   ![](assets/6_4_workstation_metricdim_create_metric.png)

   Du kan lägga till egna [måttuttryck](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html) eller klippa ut och klistra in från en annan måttredigerare eller visualisering. Syntaxfel, formelfel, odefinierade filter och andra fel rapporteras i guiden.

1. Klicka på **[!UICONTROL Next]**.

## Steg 2: Formatera och ange buffertar {#section-5bddf3cd306545d7806a501637f80f77}

1. Välj ett format för den nya metriska toningen.

   ![](assets/6_4_workstation_metricdim_format_metric.png)

   Formatet definierar hur måttet presenteras när det öppnas i en visualisering. Dessa format är valda [utskriftsstandarder](http://www.cplusplus.com/reference/cstdio/printf/)som definieras nedan:

   ```
   %[flags][width][.precision][length][specifier]
   % 0.2lf = % _ [flags] 0 [width] .2 [.precision] l [length] f[ specifier]
   ```

   I **[!UICONTROL Preview]** fältet visas ett värde baserat på det valda måttet och formatet.

1. Uttryck för Lägg till antal buffertar.

   Du kan definiera en måtttoning med olika intervall, eller intervall. Detta returnerar delmängder av element baserat på storlek, t.ex. [0-4], [5-10],..). Elementen på dimensionsnivån relaterar till elementen vars intervall innehåller måttvärdet. Mer information finns i beskrivningen av hakparentesuttrycket i [Syntax för dimensionsuttryck](https://docs.adobe.com/content/help/en/data-workbench/using/client/qry-lang-syntx/c-syntx-dim-exp.html).

1. Klicka **[!UICONTROL Preview]** för att öppna tabellen med värden för Metrisk Dim innan du sparar.

   ![](assets/6_4_workstation_metricdim_preview.png)

   Registret innehåller mätvärden per metrisk dim.

1. Klicka **[!UICONTROL Show in Dimension Menu]** för att lägga till den nya dimensionen på fliken **Dimension** i **Finder**.

1. Klicka på **[!UICONTROL Next]**.

## Steg 3: Slutför och spara {#section-d9043235b18a425f9de0db668d4b1683}

1. Välj det här alternativet om du vill starta Metrisk toningsredigerare, diagramvisualisering eller tabell när du har sparat.

   | Fält | Beskrivning |
   |---|---|
   | **[!UICONTROL Launch Metric Dim Editor]** | Öppna Metrisk toningsredigerare. |
   | **[!UICONTROL Launch Graph]** | Starta en PNG-bild av tabellen. |
   | **[!UICONTROL Launch Table]** | Starta en tabell på arbetsytan med värden i kolumner som visar värden för den nya metriska dim-metoden jämfört med värdena för det valda måttet. |

1. Klicka **[!UICONTROL Finish]** och spara.

   En dialogruta öppnas där du kan spara filen. De valda alternativen för att visa värden öppnas på arbetsytan.

