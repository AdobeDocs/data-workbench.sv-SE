---
description: Versionsinformation om Data Workbench 6.2 innehåller nya funktioner, uppgraderingskrav, felkorrigeringar och kända fel.
title: Versionsinformation om Data Workbench 6.2
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 0%

---


# Versionsinformation om Data Workbench 6.2{#data-workbench-release-notes}

Versionsinformation om Data Workbench 6.2 innehåller nya funktioner, uppgraderingskrav, felkorrigeringar och kända fel.

## Nya funktioner {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.2 innehåller följande nya funktioner:

| Funktioner | Beskrivning |
|--- |--- |
| Beslutsträd | Beslutsträd är en visualisering för prediktiv analys som används för att utvärdera besökares egenskaper och relationer. Beslutsträdsbyggaren genererar en beslutsträdsvisualisering baserad på ett angivet positivt fall och en uppsättning indata. |
| Uppdatera till binärt filter i korrelationsmatris | Binärfiltret har uppdaterats med nya funktioner som kräver att du återskapar alla korrelationsmatriser med ett binärt filter som har skapats i tidigare versioner. |
| Densitetskarta | Densitetskartan är en visualisering som visar element som skuggade rektanglar inom en fyrkantig karta. |
| Attributionsprofil | För att snabbt analysera attribueringsvärden (händelser som ska attribuera ansvaret för en lyckad konvertering eller försäljning) tillhandahåller Datan Workbench en regelbaserad attribueringsprofil med funktioner för arkitekten som ställer in attribueringsrapporterna och analytikern som kör rapporterna. |
| Analysrapporter | Rapportmallar standardiserar Adobe Analytics rapporter för användare av den data workbench som använder Adobe SC-profilen. Dessa rapporter är identiska med rapporter som används i marknadsföringsrapporter och analyser (tidigare SiteCatalyst). |
| 3D-punktdiagram | En 3D-punktdiagram visar elementen i en datamåkning (t.ex. Dagar eller Referenswebbplats) i ett tredimensionellt rutnät där x-, y- och z-axlarna representerar olika mätvärden. |


## Data Workbench Client UI Updates{#data-workbench-client-ui-updates}

Data Workbench 6.2 innehåller nya uppdateringar av användargränssnittet till bokmärkespanelen, nya ikoner i arbetsytans verktygsfält, möjligheten att dra arbetsytan inom en skärm, nya snabbtangenter och uppdateringar av cirkeldiagramvisningen.

## Nya bokmärkesfunktioner {#section-e361b605441540ca8213c3fddb5e0718}

Du kan nu bokmärka viktiga arbetsytor för att snabbt gå mellan visualiseringar och rapporter som används i arbetsflödet.

**Arbeta med bokmärken**

1. Skapa ett bokmärke för en arbetsyta genom att klicka på ikonen Bokmärke ![](assets/bookmark_icon.png) i det övre högra hörnet av verktygsfältet.
1. Klicka **[!UICONTROL Add]** > **[!UICONTROL Bookmarks Panel]** i den vänstra rutan för att öppna en lista med bokmärken.

   ![](assets/bookmarks_panel.png)

1. Om du vill öppna en arbetsyta med bokmärken klickar du på namnet på arbetsytan i **[!UICONTROL Bookmark Panel]**.

   ![](assets/bookmarks_panel_left.png)

   Den valda arbetsytan öppnas. När du klickar på en annan arbetsyta med bokmärken stängs den tidigare arbetsytan och den nya arbetsytan öppnas så att du snabbt kan navigera i arbetsflödet.

**Så här tar du bort ett bokmärke:**

* På bokmärkespanelen högerklickar du och väljer **Ta bort`<bookmark title>`** för att ta bort ett markerat bokmärke, eller väljer **[!UICONTROL Clear All Bookmarks]** att ta bort alla bokmärken.

* Du kan också högerklicka på arbetsytan i miniatyrbildsvyn i arbetsytan och välja **[!UICONTROL Clear Bookmark]**.

>[!IMPORTANT]
>
>* 25 bokmärken kan sparas.
>* Om du lägger till ett bokmärke och sedan flyttar arbetsytans plats, blir bokmärket ogiltigt och måste tas bort från bokmärkespanelen och återställas.

>



## Nya ikoner i arbetsytan {#section-c108bbd1661249e79c146727ff3d2470}

Data Workbench 6.2 ersätter nu texten på arbetsytan med ikoner. Du kan fortfarande hovra över och se verktygstipset som identifierar ikonen, inklusive **[!UICONTROL File]**, **[!UICONTROL Add]** och **[!UICONTROL Export]**.

![](assets/new_icons.png)

En ny **[!UICONTROL Help]** ikon läggs till för att komma åt dokumentationen och andra kunskapscenter, inklusive följande länkar:

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
   <td colname="col2">Öppna på hjälpsidan för <span class="uicontrol"> Adobe Marketing Reports &amp; Analytics</span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Idea Exchange </td> 
   <td colname="col2">Öppna inloggningen <span class="uicontrol"> för</span>Idea Exchange. På den här onlineportalen kan användare tillhandahålla uppdateringsändringar och förbättringsidéer till Data Workbench. Alla användare kan sedan rösta på dessa kundfokuserade idéer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hjälp </td> 
   <td colname="col2">Öppna <span class="uicontrol"> Datans Workbench dokumentation</span>. <p>Du kan också trycka på <span class="uicontrol"> &lt;F1&gt;</span> för att öppna hjälpen i en arbetsyta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Om </td> 
   <td colname="col2">Öppna för att identifiera <span class="uicontrol"> klientversionen</span> av data workbench. </td> 
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

Med de nya snabbtangenterna kan du ändra storlek på och anpassa arbetsytorna mellan fönster- och fullsidesvyer.

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

## Felkorrigeringar {#section-8704a9ac358246cd81233dd0982d534f}

* Uppdaterade Visual Site Lookup-filen för att hantera sökmotorändringar i söktermen.
* Ett felaktigt felmeddelande,&quot;Det gick inte att importera arbetsytan&quot;, har korrigerats när en arbetsyta importerades till klientarbetsstationen trots att importen lyckades.
* Anslutningsfel för arbetsstation som visar meddelandet &quot;Konflikt vid konfiguration av 412&quot; har ersatts med ett användarvänligt meddelande som identifierar systemåtgärd.
* Kommandot &quot;post&quot; kan nu köras i Report Server.
* Fel i användargränssnittet för klienten för förenklad kinesiska har korrigerats.
* Adobe Analytics har uppdaterat dataflödet som gör att Datan Workbench kan dra nytta av profiler och målgrupper som är integrerade med Adobe Experience Cloud. Alla användare av Datan Workbench måste förbereda sin miljö för övergången senast den 21 april 2014.

   Profiler och målgrupper introducerades för att ge en fullständig bild av kunderna i hela Adobe Analytics. Den här nya tjänsten finns tillgänglig i Adobe Experience Cloud för att ge ytterligare värde åt analysverktygen och börja skapa grunden för dessa funktioner i Analytics. Den nya besöksidentifieraren för Experience Cloud läggs till i dataflödet tillsammans med andra förbättringar och förbättringar för anpassning till den nya dataflödet och den globala besökaridentifieraren.
* När du importerar en arbetsyta visas ett felmeddelande även om importen lyckades.

## Krav för uppgradering {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Attributprofilen är konfigurerad för användare som har implementerat Adobe SC-profilen för att använda dataflödet från Analytics (SC/Insight). Som standard används händelserna Marketing och Conversion som standardinteraktioner som utvärderas i de regelbaserade modellerna.
* För användare av Adobe SC-profilen som uppgraderar till Data Workbench 6.2, om du inte använder standardkonfigurationerna, kontrollerar du att [!DNL x-bot_id] värdet i [!DNL SC Fields.cfg] -filen avkodas korrekt och att [!DNL x-bot_id] fältet visas korrekt i [!DNL Decoding Instructions.cfg] och i [!DNL Exclude Hit.cfg] filerna. Detta blir bara ett problem om du har ändrat konfigurationsfilen från standardkonfigurationen.

* Om du har tagit bort oanvända fält i filen **[!UICONTROL Dataset]** > **[!UICONTROL Log Processing]** > **[!DNL SC Fields.cfg]** för Adobe SC-profilen måste du uppdatera för att få plats med de uppdaterade fältvärdena som används för attributprofilen.

## Kända fel {#section-dbb307639835493a83409f5f461932b8}

* När 3D-punktritstiftsvisualisering innehåller bildtexter kan zoomningen visa områden utanför visualiseringens kant.

   Tillfällig lösning: Zooma först 3D-punktdiagram och lägg sedan till bildtexter i visualiseringen.
* Om du drar mätvärden från panelen Finders till Metrisk förklaring utanför måttkolumnen tas metrisk förklaring bort från arbetsytan.

   Tillfällig lösning: Användare som vill dra mätvärden till metrisk förklaring bör släppa i den första kolumnen (metrisk kolumn).
* Arbetsytan Skriv ut med sidofältet och alternativen Båda inkluderar inte copyrightinformationen på den utskrivna sidan.
* Om du använder Workstation i en fjärrskrivbordssession kraschar det när arbetsytorna byter namn.
* (I förenklad kinesiska version) Faktiska rapportutdata är giltiga i rapportservern, men ämnesrader och filnamn för bilagor i e-postmeddelanden är dubblerade.
* (I förenklad kinesisk version) När du använder automatisk radbrytning i kalkylbladsvisualisering radbryts inte lokaliserade ord korrekt vilket resulterar i att skräptecken läggs till i strängen.
* (I version för förenklad kinesiska) Det går inte att starta Insight.exe om installationskatalogen har ett namn med tecken som inte är engelska.

   Tillfällig lösning: Behåll standardnamn eller byt namn med endast engelska tecken i mappsökvägen för att starta körbara filer.

