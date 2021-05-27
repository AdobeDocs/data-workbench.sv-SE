---
description: Text eller uttryck kan anges i valfri cell i ett kalkylblad.
title: Arbeta med data i kalkylblad
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
exl-id: 40d9211b-8f5c-4051-8f93-638ffacf45bd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Arbeta med data i kalkylblad{#work-with-data-in-worksheets}

Text eller uttryck kan anges i valfri cell i ett kalkylblad.

Alla uttryck i ett kalkylblad föregås av ett likhetstecken (=) såvida du inte använder [!DNL eval( )], vilket behandlar texten i den refererade cellen som ett uttryck.

En fullständig lista över metrisk syntax, dimensioner och filtersyntaxregler finns i [Query Language Syntax](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

**Skriva data i ett kalkylblad**

1. Klicka två gånger på en cell i kalkylbladet för att öppna redigeringsläget. Den markerade cellen markeras.
1. Skriv eller klistra in önskade data i cellen.

**Kopiera och klistra in från en cell till en annan**

1. Högerklicka på cellen som innehåller de data som du vill kopiera och klicka på **[!UICONTROL Copy]**.
1. Högerklicka på den cell där du vill klistra in kopierade data och klicka på **[!UICONTROL Paste]**.

Data Workbench uppdaterar automatiskt referenserna i den nya cellen så att de refererar till rätt kolumner och rader.

**Kopiera och klistra in från en grupp celler till en annan**

1. Markera cellerna som innehåller de data som du vill kopiera.
1. Högerklicka på cellerna som innehåller de data som du vill kopiera och klicka på **[!UICONTROL Copy]**.
1. Högerklicka på den första cellen där du vill börja klistra in kopierade data och klicka på **[!UICONTROL Paste]**. Data klistras in i den första cellen och under den.

Data Workbench uppdaterar automatiskt referenserna i den nya cellen så att de refererar till rätt kolumner och rader.

**Infoga en kolumn**

* Högerklicka på en kolumn och klicka på **[!UICONTROL Insert Column]**. Den nya kolumnen infogas till vänster om den markerade kolumnen.

**Ta bort en kolumn**

* Högerklicka på den kolumn som du vill ta bort och klicka på **[!UICONTROL Delete Column]**. Kolumnen tas bort.

**Infoga en rad**

* Högerklicka på en rad och klicka på **[!UICONTROL Insert Row]**. Den nya raden infogas ovanför den markerade raden.

**Ta bort en rad**

* Högerklicka på raden som du vill ta bort och klicka på **[!UICONTROL Delete Row]**. Raden tas bort.

**Ändra storlek på en kolumn**

1. Placera markören över delningslinjen till höger om den kolumn vars storlek du vill ändra i kolumnrubrikraden.
1. Klicka och dra åt höger för att öka bredden på kolumnen eller åt vänster för att minska bredden på kolumnen.

**Formatera en cell**

1. Högerklicka på cellen och klicka på **[!UICONTROL Format]**.

   ![](assets/mnu_Worksheet_Format.png)

1. Klicka på önskat format på menyn med tillgängliga alternativ:

<table id="table_5788E01E52CC44E7927A0D23760D9EDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menyalternativ </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nummer </p> </td> 
   <td colname="col2"> <p>Tillämpar det markerade numeriska formatet på data, t.ex. tid, datum, procent eller decimal. </p> <p>Klicka på <span class="uicontrol"> Standard</span> om du vill ta bort den markerade formateringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Justera </p> </td> 
   <td colname="col2"> <p>Justerar data i cellen åt vänster, mitten eller höger. Standardjusteringen är kvar. </p> <p>Klicka på <span class="uicontrol"> Standard</span> om du vill ta bort den markerade formateringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Färg </p> </td> 
   <td colname="col2"> <p>Den valda teckenfärgen används på cellens data. Standardteckenfärgen är vit. </p> <p>Klicka på <span class="uicontrol"> Standard</span> om du vill ta bort den markerade formateringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indikator </p> </td> 
   <td colname="col2"> <p>Skapar en måttindikator med den här cellen. Mer information finns i <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183"> Skapa måttindikatorer</a>. </p> <p>Klicka på <span class="uicontrol"> Standard</span> om du vill ta bort den markerade formateringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indatacell </p> </td> 
   <td colname="col2"> <p>Gör den markerade cellen till en indatacell. Mer information finns i <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590"> Skapa indataceller</a>. </p> <p>Klicka på <span class="uicontrol"> Standard</span> om du vill ta bort den markerade formateringen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kortkommandon {#section-05301f4d2c60418e86902635a7aeee20}

I kalkylblad kan du använda många av de grundläggande kortkommandona för redigering som du kan använda i valfri textredigerare, t.ex. Anteckningar eller Microsoft Word.

I följande tabell visas de grundläggande kortkommandona som du kan använda när du anger data i ett kalkylblad.

<table id="table_8E6F73F253B3451CA1DE45EE4F4E69EF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Genväg </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Piltangenter </p> </td> 
   <td colname="col2"> <p>Gå från cell till cell i kalkylbladet med upp-, ned-, vänster- och högerpilarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>Redigera cellen genom att placera markören i cellen som du har markerat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Retur </p> </td> 
   <td colname="col2"> <p>Slutför redigeringen av den markerade cellen. Markören tas bort från cellen och cellinnehållet återspeglar redigeringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esc </p> </td> 
   <td colname="col2"> <p>Avbryt redigeringen av den markerade cellen. Markören tas bort från cellen och cellinnehållet återställs till det som var innan du började redigera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta bort </p> </td> 
   <td colname="col2"> <p>Ta bort innehållet i cellerna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>Markera innehållet i cellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+C </p> </td> 
   <td colname="col2"> <p>Kopiera innehållet i cellerna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+x </p> <p>Skift+Delete </p> </td> 
   <td colname="col2"> <p>Kopiera och ta bort innehållet i cellerna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+V </p> <p>Skift+Infoga </p> </td> 
   <td colname="col2"> <p>Klistra in innehållet i de celler som du har kopierat i de markerade cellerna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+z </p> </td> 
   <td colname="col2"> <p>Ångra inmatning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Skift+z </p> </td> 
   <td colname="col2"> <p>Gör om att skriva. </p> </td> 
  </tr> 
 </tbody> 
</table>
