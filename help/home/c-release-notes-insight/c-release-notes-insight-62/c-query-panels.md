---
description: Använd Finder-panelerna i Data Workbench för att välja mått, dimensioner och filter. Panelerna har stöd för sökning, sorteringsalternativ samt möjlighet att dra och släppa.
title: Finders
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 0%

---


# Findrar{#finders}

Använd Finder-panelerna i Data Workbench för att välja mått, dimensioner och filter. Panelerna har stöd för sökning, sorteringsalternativ samt möjlighet att dra och släppa.

Du kan öppna en Finder-panel i den vänstra sidlisten eller på en arbetsyta.

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensions Finder </th> 
   <th colname="col2" class="entry"> Metrics Finder </th> 
   <th colname="col3" class="entry"> Filter Finder </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>En lista med alla dimensioner i frågemodellen. </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>En lista med alla mätvärden i din frågemodell. </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>En lista över alla filter som har skapats för din organisation. </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**Så här öppnar du en Finder:**

* Högerklicka på en arbetsyta och välj **[!UICONTROL Tools]** > **[!UICONTROL Finder]**.

   Fönstret Finder med flikar för Metrisk, Dimensioner och Filter öppnas på arbetsytan.

* Högerklicka i det vänstra sidfältet och välj **[!UICONTROL Add]** > **[!UICONTROL Finder]**.

   Fönstret Finder öppnas i den vänstra panelen.

**Finder** innehåller följande funktioner:

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktioner i Finder </th> 
   <th colname="col2" class="entry"> Detaljer </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Dra och släpp</b> </td> 
   <td colname="col2"> <p> Du kan dra och släppa mått eller mätvärden från panelen till en visualisering på arbetsytan för att ändra måtten eller lägga till nya mätvärden. </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">Håll ned <span class="uicontrol"> &lt;Ctrl&gt;</span> och <span class="uicontrol"> &lt;Alt&gt;</span> och välj mått eller mått på panelen Finder. </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">Dra en ny dimension från rutan och släpp den i visualiseringen för att ändra eller lägga till dimensioner. </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">Om du vill lägga till mätvärden drar du ett nytt mätvärde från rutan och släpper det i måtthuvudet för den valda visualiseringen. </li> 
    </ol> <p>Detta fungerar för alla relevanta visualiseringar, inklusive tabeller, besökarkluster, korrelationsmatris, punktdiagram och 2D-stapeldiagram (beroende på axeln). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Sök</b> </td> 
   <td colname="col2">I rutan <span class="uicontrol"> Sök</span> på panelen Finder kan du filtrera namn på Dimensioner, mått och filter. 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>Mönstermatchning (enkel sökning med glob). Börja skriva namnet på en obligatorisk dimension, måttenhet eller filterentitet i sökfältet. Endast matchande strängar som finns någonstans i namnet filtreras och visas i Finders-rutan. </p> <p>Ange till exempel: </p> <code><b>Search:</b>click</code> <p>Du kan få följande resultat i Dimensions Finder: </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>Med standardmönstermatchning kan du använda jokertecken, t.ex. . (punkt), "?" och "*" (stjärna). </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>Reguljära uttryck. Mer komplexa reguljära uttryck stöds också för utökad sökfunktion. Lägg till prefixet "re:" före söktermen (inga blanksteg) som ska tolkas som ett reguljärt uttryck. </p> <p>Ange till exempel: </p> <code><b>Search:</b>re.*ip</code> <p>Du kan få följande resultat i Dimensions Finder: </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>Mer detaljerad sökinformation finns i <a href="https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external"> reguljära uttryck</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Dimension</b> </td> 
   <td colname="col2">På fliken Dimension kan du högerklicka på tabbrubriken för att sortera efter dimensionstypen. <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">Attribut - Dimensioner som bygger på besökarens egenskaper, produkter, geografi, tid, video och andra attribut. </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">Kluster - Dimensioner som byggts i klusterbyggaren. </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">Bakgrundsmusik - Dimensioner som är inbyggda i poängen för benägenhet. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Etikett</b> </td> 
   <td colname="col2">På varje flik kan du högerklicka och välja <span class="uicontrol"> Label</span> för att byta namn på Finder-rutan. <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>Standardetiketterna för Dimensioner, mått och filter kan ändras till ett fliknamn som uppfyller organisationens regler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Lägg till objekt</b> </td> 
   <td colname="col2">På varje flik kan du högerklicka och välja <span class="uicontrol"> Lägg till objekt</span> för att öppna en tabell och manuellt lägga till Dimensioner, mått och filter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Fältet Finders</b> </td> 
   <td colname="col2">Högerklicka i fältet <span class="uicontrol"> Finders</span> i det vänstra sidofältet för att öppna en meny för ytterligare funktioner. <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Stäng</b> </td> 
   <td colname="col2">Högerklicka i fältet <span class="uicontrol"> Finders</span> och välj <span class="uicontrol"> Stäng</span> för att stänga rutan Finders. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Spara</b> </td> 
   <td colname="col2">Spara listan lokalt genom att högerklicka i sidhuvudsfältet och välja alternativet <span class="uicontrol"> Spara</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Exportera</b> </td> 
   <td colname="col2">Du kan exportera en lista med valda mått, mätvärden eller filter från panelen Finder genom att högerklicka i fältet Finders och välja <span class="uicontrol"> Export</span> på menyn. <p> Lägg till ett namn och exportera till Microsoft Excel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Kopiera</b> </td> 
   <td colname="col2"> Kopiera en lista med Dimensioner, mått eller filter. Du kan kopiera som en fil eller som en bild i Mörk bakgrund, Ljus bakgrund eller Monokrom. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Minimera</b> </td> 
   <td colname="col2"> Minimera rutan Finder. Endast fältet Finders visas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>utan kanter</b> </td> 
   <td colname="col2"> Visar en ruta utan kantlinjer för Finders på arbetsytan (men inte i den vänstra sidofältet). </td> 
  </tr> 
 </tbody> 
</table>

