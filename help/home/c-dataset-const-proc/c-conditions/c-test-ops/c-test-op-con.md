---
description: Information om teståtgärdsvillkor, inklusive jämför, inte tom, omfång, reguljära uttryck och strängmatchning.
solution: Analytics
title: Villkor för teståtgärd
topic: Data workbench
uuid: 6a117569-1372-4095-972b-76289a45f19e
translation-type: tm+mt
source-git-commit: ed7597393049099e08586716163cbd1cca50c5fa
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 2%

---


# Villkor för teståtgärd{#test-operation-conditions}

Information om teståtgärdsvillkor, inklusive jämför, inte tom, omfång, reguljära uttryck och strängmatchning.

* [Jämför](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)
* [Inte tom](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)
* [Intervall](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1db31583bb09418b8f49481a897b08a6)
* [Reguljärt uttryck](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-ae9c016502cb44128760c58f2d2d5297)
* [Strängmatchning](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)

## Jämför {#section-fb2bdb3838504099b324b9838cdeeaac}

I [!DNL Compare] villkoret jämförs sträng- eller numeriska värden. Vid jämförelser av strängvärden kan du ange om skiftläge ska beaktas.

Parametrarna för [!DNL Compare] villkoret beskrivs i följande tabell:

<table id="table_05B1FBB2AED242D99081E62BE2FBEC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Skiftlägeskänslig </td> 
   <td colname="col2">Sant eller falskt. Används endast om typen är <span class="wintitle"> LEXICAL</span>. Om värdet är false betraktas gemener och versaler som lika. </td> 
   <td colname="col3"> sant </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om villkoret. </td> 
   <td colname="col3"> Kommentarer </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata A </td> 
   <td colname="col2"> Det första av de två värdena som ska jämföras. Detta värde representerar den vänstra operanden i villkoret. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata B </td> 
   <td colname="col2"> Det andra av de två värdena som ska jämföras. Detta värde representerar den högra operanden i villkoret. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Åtgärd </td> 
   <td colname="col2"> <p>Jämförelseåtgärden. Följande åtgärder är tillgängliga (och deras betydelse): 
     <ul id="ul_74F3C298E9CC4FE89897BA0052A9EB9F"> 
      <li id="li_1605FA73474E404A84056D40E7082623"> = eller == (Indata A är lika med indata B) </li> 
      <li id="li_F694A262ED7A4787B2A68B877339620C"> &lt;&gt; eller != (Indata A är inte lika med indata B) </li> 
      <li id="li_1A75437E23B64BEB92297E1C771092B0"> &lt; (Indata A är mindre än indata B) </li> 
      <li id="li_B80ED6BE9DEA41FE84BC6BA3B7759276"> &lt;= (Indata A är mindre än eller lika med indata B) </li> 
      <li id="li_93148F34065F489E8E198DFB9F9F0E70"> &gt; (Indata A är större än indata B) </li> 
      <li id="li_8A98EE9AED2445429805169040BB253D"> &gt;= (Indata A är större än eller lika med indata B) </li> 
     </ul> </p> </td> 
   <td colname="col3"> = </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Typ </td> 
   <td colname="col2">Den typ av jämförelse som ska göras. Tillgängliga typer är <span class="wintitle"> LEXICAL</span>, <span class="wintitle"> NUMERIC</span>och <span class="wintitle"> DATETIME</span>. Beskrivningar av typerna finns i Testtyper <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> för teståtgärder</a>. </td> 
   <td colname="col3"> <span class="wintitle"> LEXICAL</span> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet används ett [!DNL Compare] villkor för att definiera [!DNL Log Entry Condition]. När data workbench-servern läser varje händelsedatapost jämförs de numeriska värdena x-age och 55. Om x-age för en given loggpost är mindre än eller lika med 55, inkluderas loggposten i datauppsättningens konstruktionsprocess.

![](assets/cfg_Condition_CompareCondition.png)

## Inte tom {#section-1decb9d887894073a1b6b3d985729ac8}

Villkoret kontrollerar om ett fält innehåller ett värde eller är tomt. [!DNL Not Empty] Villkoret är uppfyllt för alla loggposter vars värde för [!DNL Input] fältet inte är tomt.

Parametrarna för [!DNL Not Empty] villkoret beskrivs i följande tabell:

| Parameter | Beskrivning | Standard |
|---|---|---|
| Kommentarer | Valfritt. Anteckningar om villkoret. | Kommentarer |
| Indata | Namnet på det fält från loggposten som ska kontrolleras. |  |

I det här exemplet används x-some-fält som indata och testas om fältet inte är tomt. Villkoret är uppfyllt om fältet fylls i.

![](assets/cfg_Condition_NotEmpty.png)

## Intervall {#section-1db31583bb09418b8f49481a897b08a6}

Villkoret tar ett indatafält och avgör om värdet i det fältet faller, inkluderande, inom de angivna parametervärdena för minimum (Min) och maximum (Max). [!DNL Range]

Parametrarna för [!DNL Range] villkoret beskrivs i följande tabell:

<table id="table_1587D8D333804FC28024C0DFC2F2D4D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Skiftlägeskänslig </td> 
   <td colname="col2">Sant eller falskt. Används endast om <span class="wintitle"> typen</span> är <span class="wintitle"> LEXICAL</span>. Om värdet är false betraktas gemener och versaler som lika. </td> 
   <td colname="col3"> sant </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om villkoret. </td> 
   <td colname="col3"> Kommentarer </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Namnet på fältet från loggposten som ska användas som indata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min </td> 
   <td colname="col2"> <p>Lägre intervall. </p> <p> Parameterns värde måste vara ett literalt värde eller en sträng - inte ett fältnamn. Om du använder ett datum för det här fältet måste du ange en tidszon. En lista med förkortningar av tidszoner som stöds finns i <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder</a>. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max </td> 
   <td colname="col2"> <p>Intervallets övre gräns. </p> <p> <p>Obs! Parameterns värde måste vara ett literalt värde eller en sträng - inte ett fältnamn. Om du använder ett datum för det här fältet måste du ange en tidszon. En lista med förkortningar av tidszoner som stöds finns i <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Tidszonskoder</a>. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Typ </td> 
   <td colname="col2">Den typ av jämförelse som ska göras. Tillgängliga typer är <span class="wintitle"> LEXICAL</span>, <span class="wintitle"> NUMERIC</span>och <span class="wintitle"> DATETIME</span>. Beskrivningar av typerna finns i Testtyper <a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a"> för teståtgärder</a>. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet används ett [!DNL Range] villkor för att definiera [!DNL Log Entry Condition]. När data workbench-servern läser varje [!DNL event data] post jämförs de numeriska värdena x-age och 55. Om x-age för en viss loggpost är minst 55, inkluderas loggposten i datauppsättningens konstruktionsprocess. I det här exemplet utförs samma funktion som i [!DNL Compare] villkorsexemplet. Se [Jämför](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac).

>[!NOTE]
>
>Om parametern Min eller Max lämnas tom ersätter data workbench-servern de lägsta eller högsta tillgängliga heltalsvärdena. Det lägsta värdet är noll (0) och det högsta värdet är oändligt.

![](assets/cfg_Condition_RangeCondition.png)

## Reguljärt uttryck {#section-ae9c016502cb44128760c58f2d2d5297}

I [!DNL Regular Expression] villkorstestet används mönstermatchning för reguljära uttryck (se [Reguljära uttryck](../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)) för att avgöra om värdet i det angivna inmatningsfältet innehåller en sträng som matchar ett av de mönster som anges i parametern Matchar.

Om indata är en vektor med strängar används bara det första värdet i vektorn för testet. Villkoret [!DNL Regular Expression] utför fullständiga strängjämförelser. Om du vill identifiera delsträngar måste du lägga till&quot; före och efter.*&quot; till strängen.

Parametrarna för [!DNL Regular Expression] villkoret beskrivs i följande tabell:

<table id="table_0BF5F89F87C9493B8DABA97620074FAD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Skiftlägeskänslig </td> 
   <td colname="col2"> Sant eller falskt. Om värdet är false betraktas gemener och versaler som lika. </td> 
   <td colname="col3"> sant </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om villkoret. </td> 
   <td colname="col3"> Kommentarer </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Namnet på fältet från loggposten som ska användas som indata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matchar </td> 
   <td colname="col2"> <p>Mönster för reguljära uttryck som ska matchas mot indatafältets värde. </p> <p> <b> Lägga till ett mönster för reguljära uttryck</b> 
     <ol id="ol_6D6467FF74334DEA8E8625C3B155D11D"> 
      <li id="li_9E13A63558FF44749C2E49BD50B7F770">Högerklicka på <span class="uicontrol"> Matchar</span>. </li> 
      <li id="li_195A2F3B6B9442F5B1DACDE0FC96CE5C">Klicka på <span class="uicontrol"> Lägg till nytt</span> &gt; <span class="uicontrol"> Reguljärt uttryck</span>. </li> 
      <li id="li_225E98F8EF39426A9483B86EA2CFE6DF">Ange det reguljära uttrycket i textrutan. </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet visas hur villkoret används för att matcha ett fält med data som samlats in från webbplatstrafiken. [!DNL Regular Expression] Villkoret returnerar bara true om fältet cs(reference-query) innehåller en sträng som matchar det reguljära uttrycket `campaign=C[1-9][0-9]{4}`. Det här reguljära uttrycket matchar alla strängar som innehåller `campaign=C12345`. Mönstret matchar dock inte strängen `campaign=C0123&` eftersom det första tecknet efter `C` inte finns i intervallet `1-9`.

![](assets/cfg_Condition_RegularExpression.png)

## Strängmatchning {#section-f8d132085c6b4500bfbe4515b848142f}

Villkorstestet [!DNL String Match] för strängens likhet. Det tar ett angivet fält som indata och testar värdet för det fältet i varje loggpost mot strängarna som anges i operationens Matchar-parameter. Om någon av dessa skiftlägeskänsliga matchningssträngar är densamma som värdet i det angivna indatafältet returnerar åtgärden true. Om villkoret inte [!DNL StringCondition] innehåller några matchande strängar returneras false. Om indata är en vektor med strängar används bara det första värdet (strängen) i vektorn för testet.

<table id="table_BD599BAA5DD54B278813B6C38AC8DE6B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Skiftlägeskänslig </td> 
   <td colname="col2"> Sant eller falskt. Om värdet är false betraktas gemener och versaler som lika. </td> 
   <td colname="col3"> sant </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om villkoret. </td> 
   <td colname="col3"> Kommentarer </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indata </td> 
   <td colname="col2"> Namnet på fältet från loggposten som ska användas som indata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matchar </td> 
   <td colname="col2"> <p>Strängen/strängarna som ska matchas mot indatafältets värde. </p> <p> <b>Lägga till en sträng</b> 
     <ol id="ol_9E32218C771445D88357960475FAD6EB"> 
      <li id="li_A700747858D0470491783E9B3933DAFE">Högerklicka på <span class="uicontrol"> Matchar</span>. </li> 
      <li id="li_9D1A2462EA404B0F84426176737CAFED">Klicka på <span class="uicontrol"> Lägg till nytt</span> &gt; <span class="uicontrol"> String</span>. </li> 
      <li id="li_E84D2439B59548E5B1803C64A295A18E">Ange önskad sträng i textrutan. </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet används data som samlats in från webbplatstrafiken för att illustrera hur [!DNL String Match] villkoret används. Villkoret testar om indatafältet (cs-uri-stam) matchar någon av de två strängarna som anges i parametern Matches, och det fungerar om fältet cs-uri-stam antingen är den exakta strängen [!DNL /navigation/footer.asp] eller den exakta strängen [!DNL /navigation/header.asp].

![](assets/cfg_Condition_StringMatch.png)

