---
description: Förtroendeförklaringar hjälper dig att avgöra sannolikheten för att de siffror du ser beror på en chans och förstå eventuella avvikelser i data.
solution: Analytics
title: Förtroendeförklaringar
topic: Data workbench
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Förtroendeförklaringar{#confidence-legends}

Förtroendeförklaringar hjälper dig att avgöra sannolikheten för att de siffror du ser beror på en chans och förstå eventuella avvikelser i data.

Även om du inte är samplingsdata kan du inte extrapolera siffrorna från en viss tidsperiod eller delmängd till andra tidsperioder eller delmängder med full säkerhet. Med hjälp av förtroendeförklaringen kan du utforska sannolikheten för att talen hamnar inom ett visst intervall.

Om ni ser verkliga data som ett stort experiment innebär verkligheten fortfarande en chans, även när ni arbetar med exakta siffror. Att veta hur många personer som slutförde en transaktion mellan 08:00 och 12:00 på en tisdag innebär inte att exakt samma antal kommer att göras nästa tisdag.

I följande förklaring visas tillförlitlighetsinformation om konverteringsmåttet, medan följande tabell innehåller mer information om vad varje datapunkt betyder.

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Mått eller formel </p> </td> 
   <td colname="col2"> <p>Måttnamnet eller måttuttrycket som du vill visa konfidensinformation för. Alla markeringar du gör på arbetsytan visas i teckenförklaringen. I det här exemplet visas information om konverteringsmåttet. </p> <p>Mer information om syntaxregler för att ange ett uttryck finns i <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> Query Language Syntax</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mätvärde </p> </td> 
   <td colname="col2"> <p>Värdet på faktiska insamlade data. I det här exemplet är konverteringsgraden för den aktuella markeringen 2,3 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardavvikelse </p> </td> 
   <td colname="col2"> <p>Standardavvikelsen för det uppmätta värdet. I det här exemplet är standardavvikelsen för konverteringsgraden för den aktuella markeringen 0,1 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Värdet "true" </p> </td> 
   <td colname="col2"> <p>Sannolikheten för att det uppmätta värdet ligger inom det intervall som anges för varje sannolikhet. I det här exemplet kan du vara 90 % säker på att det uppmätta värdet ligger mellan 2,1 % och 2,4 % om det här"verkliga experimentet" upprepas om och om igen. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>När du analyserar resultatet av en beräkning måste du ta hänsyn till följande viktiga faktorer: >
>* Siffrorna är uppskattningar. Om du upprepar samma beräkningar med en annan datauppsättning får du ett annat resultat. Detta kallas slumpmässig variation.
>* Extrapoleringar till högre sannolikheter beror på ett antagande om normalitet som inte är korrekt för alla mätvärden. Därför är värdena för 99 % sannolikhet mindre tillförlitliga än värdena för 90 % sannolikhet.
>
>
Om du behöver mer exakta siffror bör du rådfråga en expert i statistik.

## Ändra mätvärden eller formler {#section-7f09ff84c3514f26b78d29294e1f03d9}

* Klicka i fältet och skriv det önskade måttet eller uttrycket i den förtroendeförklaring som visas **[!UICONTROL Metric or Formula]** . Mer information om syntaxregler för uttryck finns i [Query Language Syntax](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

## Exportera till Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

Mer information om att exportera fönster finns i [Exportera fönsterdata](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
