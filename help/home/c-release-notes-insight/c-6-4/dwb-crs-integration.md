---
description: Med exportfunktionen i Customer Record Service (CRS) kan ni exportera Data Workbench data till Adobe Analytics Core Services för att integrera med andra analysfunktioner, inklusive rapporter och analyser.
title: Exportera till bastjänsterna i Analytics
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
exl-id: 573085e8-2260-4872-be90-a84ad61145bb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---

# Exportera till bastjänsterna i Analytics{#exporting-to-analytics-core-services}

Med exportfunktionen i Customer Record Service (CRS) kan ni exportera Data Workbench data till Adobe Analytics Core Services för att integrera med andra analysfunktioner, inklusive rapporter och analyser.

>[!NOTE]
>
>För att funktionen för CRS-export ska fungera måste besökarens analys-ID baseras på Experience Cloud ID-tjänsten (ECID). ECID kan vara ifyllt i Data Workbench för en besökare, men om klienten befinner sig i respitperioden eller besökarens cookie inte har ersatts med ECID fungerar inte CRS-exporten för den besökaren. Mer information finns i [Identifiera besökare](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) och [giltighetsperiod för ID-tjänst](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html).

Från en **detaljtabell** (högerklicka **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** i en arbetsyta) kan du ange attributvärden och de variabler som krävs för att integrera med Analytics rapporter och analyser (med Adobe Pipeline Services).

1. **Högerklicka på tabellrubriken och klicka på Ny kundposttjänst.**

   ![](assets/6_4_CRS.png)

1. **Ge exportfilen ett namn och spara.**

   Exportfilens redigeringsfönster öppnas.

1. **** **OpenQuery > CRS Configuration**.
1. **Högerklicka på CRS-attribut > Lägg till ny.**
1. **** ***EnterCRS-*** **attributparametrar**.

   Öppna den nya posten och ange eller verifiera värden i avsnittet *CRS-attribut* i exportfilen:

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Attributnamn</b> </p> </td> 
      <td colname="col2">Namnet på variabeln <i>Kundattribut</i> som visas i <i>Rapporter och analyser</i>. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Attributtyp</b> </td> 
      <td colname="col2"> <p>Den här parametern accepterar värden för (<i>int</i>, <i>sträng</i>). </p> <p>Obs! Om ett attribut är <b>inte</b> prenumererat på i Analytics: <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">Attributet skapas med alla giltiga attributtyper som stöds av Analytics (i den här versionen är det begränsat till endast <i>sträng</i> och <i>int</i>). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Om en ogiltig attributtyp anges visas ett felmeddelande om att det inte gick att prenumerera på Analytics. </li> 
      </ul> </p> <p>Om ett attribut redan är <b></b> prenumererat på i Analytics: </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Var noga med att ange rätt attributtyp för det attribut som redan prenumererar på. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Om du anger fel typ för attributet beror dess beteende på Analytics' hantering av attributtyper. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Fältnamn</b> </p> </td> 
      <td colname="col2">Namnet på dimensionen eller mätvärdet som attributvärdena väljs från. <p>Obs! <i><b>Fältnamnet</b></i> under <i>CRS-attribut</i> ska vara samma som <b><i>Utdatafält</i> &gt; <i>Fältnamn</i></b> (som fylls i automatiskt baserat på det valda attributet). Om <i>fältnamnet</i> är ogiltigt kommer exporten inte att köras. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Högerklicka **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Ange **[!UICONTROL Report Suite ID]**.

   Öppna den nya posten och ange eller verifiera värden i avsnittet *Report Suite* i exportfilen:

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Report Suite</b> </td> 
      <td colname="col2">ID för rapportsviten i <i>Rapporter och analyser</i> som identifierar variablerna <i>Kundattribut</i> som exporteras. <p> <p>Obs! Med <i>Rapporter och analyser</i> kan du lägga till i flera rapportsviter, men med Data Workbench 6.4 kan du bara exportera en enda rapportserie som identifieras vid <i>index 0</i>. <p>Rapportsvitens värde som anges i det här fältet är rapportsvitens ID (och inte namnet på rapportsviten). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Ange parametern ECID-fält.

   **ECID-fält**: Namn på den dimension i din profil som representerar Adobe Experience Cloud-id:t. Detta är ett obligatoriskt fält och alla ogiltiga dimensionsvärden som anges exporteras inte.

1. (valfritt) Slutför parametern Fält för besöks-ID.

   **Fält** för besökar-ID: Om användaren vill skicka ett annat anpassat ID för en besökare i sina data anger han/hon namnet på dimensionen som representerar det anpassade besökar-ID:t här. Det här är ett valfritt fält och kan lämnas tomt.
