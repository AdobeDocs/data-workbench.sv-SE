---
description: Omformningen RETransform (reguljärt uttryck) är en mönstermatchningsomformning som använder reguljära uttryck för att ange ett mönster att söka efter och hämta i indata och lagrar den hämtade strängen i ett angivet utdatafält.
solution: Analytics
title: RETransform
topic: Data workbench
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# RETransform{#retransform}

Omformningen RETransform (reguljärt uttryck) är en mönstermatchningsomformning som använder reguljära uttryck för att ange ett mönster att söka efter och hämta i indata och lagrar den hämtade strängen i ett angivet utdatafält.

Reguljära uttryck utvärderas mot hela indatasträngen. Om indata inte matchar mönstret som anges i det reguljära uttrycket hämtas inga data. En kort guide till hur du använder reguljära uttryck finns i [Reguljära uttryck](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>Omvandlingen [!DNL RETransform] fungerar på ungefär samma sätt som [!DNL REMatch] omformningen (se [REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)), som skapar ett utdatafält för varje hämtat delmönster i det reguljära uttrycket. Du kan tänka dig [!DNL RETransform] som en kombination av [!DNL REMatch] och [!DNL Format] omformningar. Om åtgärdsparametern (se Åtgärd i följande tabell) är inställd på &quot;RESULTS&quot; [!DNL RETransform] fungerar den som en kombination av [!DNL REMatch] och [!DNL Union] omformningar.

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Beskrivande namn på omformningen. Här kan du ange valfritt namn. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om omvandlingen. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor som den här omformningen används under. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standard </td> 
   <td colname="col2"> Det standardvärde som ska användas om villkoret är uppfyllt och indatavärdet antingen inte är tillgängligt eller om det reguljära uttrycket inte matchar indatavärdet. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Åtgärd </td> 
   <td colname="col2"> <p>Anger hur resultatet behandlas. Standardinställningen för RESULTS tar helt enkelt de matchande mönstren och skapar en vektor med strängar från de mönster som extraheras. </p> <p> Alternativt kan åtgärden vara en formateringssträng för att skapa enkla strängutdata med ett visst format. Med den här tekniken anger du talet som motsvarar placeringen av varje matchat mönster mellan %-tecknen. Det första matchade mönstret skulle till exempel vara %1% och det tredje matchade mönstret skulle vara %3%. Du anger bokstavligen andra tecken i formateringssträngen. </p> </td> 
   <td colname="col3"> RESULTAT </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uttryck </td> 
   <td colname="col2"> Det reguljära uttryck som används för matchning. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Det fält som det reguljära uttrycket utvärderas mot. </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> Namnet på utdatasträngen. </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL RETransform] omvandlingar kan vara mycket långsamma och kan stå för mycket av databehandlingstiden.

I det här exemplet isoleras den version av Windows-operativsystemet som en webbplatsbesökare använder och skapar ett fält av typen x-windows från det värdet. I det här fallet är utdatavärdet bara versionsnumret.

![](assets/cfg_TransformationType_RegularExpression.png)

Om du vill inkludera strängen &quot;Version&quot; framför versionsnumret för läsbarhet, ändrar du åtgärdsparametern från &quot;RESULTS&quot; till &quot;Version %1%&quot;. Om du vill inkludera ett literalt procenttecken (%) i utdata kan du undvika det med ett andra procenttecken, som i &quot;%%&quot;.
