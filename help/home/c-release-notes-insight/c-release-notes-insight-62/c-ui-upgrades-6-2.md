---
description: Data Workbench 6.2 innehåller nya uppdateringar av användargränssnittet till bokmärkespanelen, nya ikoner i arbetsytans verktygsfält, möjligheten att dra arbetsytan inom en skärm, nya snabbtangenter och uppdateringar av cirkeldiagramvisningen.
title: Data Workbench Client UI Updates
uuid: 1bc18c90-8b46-4c90-b7a7-2c6710e1e28c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---


# Data Workbench Client UI Updates{#data-workbench-client-ui-updates}

Data Workbench 6.2 innehåller nya uppdateringar av användargränssnittet till bokmärkespanelen, nya ikoner i arbetsytans verktygsfält, möjligheten att dra arbetsytan inom en skärm, nya snabbtangenter och uppdateringar av cirkeldiagramvisningen.

## Nya bokmärkesfunktioner {#section-e361b605441540ca8213c3fddb5e0718}

Du kan nu bokmärka viktiga arbetsytor för att snabbt gå mellan visualiseringar och rapporter som används i arbetsflödet.

**Arbeta med bokmärken**

1. Skapa ett bokmärke för en arbetsyta genom att klicka på ikonen Bokmärke ![](assets/bookmark_icon.png) i det övre högra hörnet av verktygsfältet.
1. Klicka på **[!UICONTROL Add]** > **[!UICONTROL Bookmarks Panel]** i den vänstra rutan för att öppna en lista med bokmärken.

   ![](assets/bookmarks_panel.png)

1. Om du vill öppna en bokmärkt arbetsyta klickar du på ett namn på arbetsytan i **[!UICONTROL Bookmark Panel]**.

   ![](assets/bookmarks_panel_left.png)

   Den valda arbetsytan öppnas. När du klickar på en annan arbetsyta med bokmärken stängs den tidigare arbetsytan och den nya arbetsytan öppnas så att du snabbt kan navigera i arbetsflödet.

**Så här tar du bort ett bokmärke:**

* Högerklicka på bokmärkespanelen och välj **Ta bort`<bookmark title>`** om du vill ta bort ett markerat bokmärke, eller välj **[!UICONTROL Clear All Bookmarks]** om du vill ta bort alla bokmärken.

* Du kan också högerklicka på arbetsytan i miniatyrbildsvyn i arbetsytan och välja **[!UICONTROL Clear Bookmark]**.

>[!IMPORTANT]
>
>* 25 bokmärken kan sparas.
>* Om du lägger till ett bokmärke och sedan flyttar arbetsytans plats, blir bokmärket ogiltigt och måste tas bort från bokmärkespanelen och återställas.

>


## Nya ikoner i arbetsytan {#section-c108bbd1661249e79c146727ff3d2470}

Data Workbench 6.2 ersätter nu texten på arbetsytan med ikoner. Du kan fortfarande hovra över ikonen och se verktygstipset som identifierar den, inklusive **[!UICONTROL File]**, **[!UICONTROL Add]** och **[!UICONTROL Export]**.

![](assets/new_icons.png)

En ny **[!UICONTROL Help]**-ikon läggs till för att komma åt dokumentationen och andra kunskapscenter, inklusive följande länkar:

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dokumentationslänkar </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Marknadsföringsrapporter och analyser </td> 
   <td colname="col2">Öppna på hjälpsidan <span class="uicontrol"> Adobe Marketing Reports &amp; Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Idea Exchange </td> 
   <td colname="col2">Öppna för inloggningen <span class="uicontrol"> Idea Exchange</span>. På den här onlineportalen kan användare tillhandahålla uppdateringsändringar och förbättringsidéer till Data Workbench. Alla användare kan sedan rösta på dessa kundfokuserade idéer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hjälp om  </td> 
   <td colname="col2">Öppna dokumentationen för <span class="uicontrol">-Datan Workbench</span>. <p>Du kan också trycka på <span class="uicontrol"> &lt;F1&gt;</span> för att öppna hjälpen i en arbetsyta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Om </td> 
   <td colname="col2">Öppna för att identifiera <span class="uicontrol">-klientversionen</span> av data workbench. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Du kan också trycka på `<F1>` för att öppna dokumentationen från en arbetsyta.

## Dra arbetsytevyer {#section-9129c340c21d45a3864c923884cd4382}

Om en arbetsyta är större än den visningsbara skärmen kan du flytta vyn så att alla element på arbetsytan visas. Du kan klicka i bakgrunden (utanför visualiseringar och tabeller) och dra skärmen för att flytta det visningsbara området inom arbetsytan. Markören ändras till en handikon när du drar vyn i arbetsyteramen.

![](assets/drag_workspace.png)

## Snabbtangenter för att ändra arbetsytevyer {#section-d8322f72423f437aa2e34f2188b1341c}

Med de nya snabbtangenterna kan du ändra storlek på och anpassa arbetsytorna mellan fönster- och fullsidesvyer. Se [Snabbreferens](https://experienceleague.adobe.com/docs/data-workbench/using/client/visualizations/c-qk-ref.html) för fler tangentbordstangenter.

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kommandon </th> 
   <th colname="col2" class="entry"> Snabbtangenter </th> 
   <th colname="col3" class="entry"> Kombinerade menykommandon </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Helskärmsläge</b>. Arbetsytan fyller skärmen och anpassar den till den nya storleken. </td> 
   <td colname="col2"><b>Ctrl plus</b> <p>Ctrl + (på knappsats) </p> <p><i>eller</i> </p> <p>Ctrl Skift + (på tangentbordet) </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">Arkiv &gt; Sidstorlek &gt; Fyllningsskärm <p><i>följt av</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">Arkiv &gt; Anpassa arbetsyta </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Fönstervy</b>. Arbetsytan visas i en standardfönstervy och anpassas till den nya storleken. </td> 
   <td colname="col2"><b>Ctrl minus</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">Arkiv &gt; Sidstorlek &gt; Standard <p><i>följt av</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">Arkiv &gt; Anpassa arbetsyta </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

