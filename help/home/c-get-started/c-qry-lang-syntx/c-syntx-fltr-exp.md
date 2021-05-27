---
description: Ett filter är ett uttryck som definierar en delmängd av data i en datauppsättning.
title: Syntax för filteruttryck
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---

# Syntax för filteruttryck{#syntax-for-filter-expressions}

Ett filter är ett uttryck som definierar en delmängd av data i en datauppsättning.

Ett filter antingen tillåter eller avvisar varje element i varje dimension enligt relationen mellan dimensionerna.

Filter kan redigeras med [!DNL Filter Editor]. Se [Filterredigerare](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

I följande tabell innehåller varje syntaxbeskrivning ett exempel på ett metriskt uttryck som använder det filtret. Sessioner[Sant] är till exempel ett mått som definieras med filtret &quot;Sant&quot;. Sessionerna[Sant]-måttet är samma som sessionsmätningen eftersom filtret Sant tillåter alla element i sessionsdimensionen.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Konstantfilter. Tillåter alla element i alla dimensioner </p> <p>Exempel: Sessioner[ Sant ] är samma som sessioner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falskt </p> </td> 
   <td colname="col2"> <p>Konstantfilter. Avvisar alla element i alla dimensioner. </p> <p>Exempel: Sessioner[ Falskt ] är alltid noll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>inte filter </p> </td> 
   <td colname="col2"> <p>Tillåter element som Filter avvisar. </p> <p>Exempel: Sessioner[ not Page="A" ] är antalet sessioner som inte besökt sida A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA och FilterB </p> </td> 
   <td colname="col2"> <p>Tillåter element som FilterA och FilterB tillåter. </p> <p>Exempel: Sessioner[ Page="A" och Page="B" ] är antalet sessioner som besökt både sida A och sida B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA eller FilterB </p> </td> 
   <td colname="col2"> <p>Tillåter element som FilterA eller FilterB tillåter. </p> <p>Exempel: Sessioner[ Page="A" eller Page="B" ] är antalet sessioner som besökt sida A, sida B eller båda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtrera efter toning </p> </td> 
   <td colname="col2"> <p>Tillåter den uppsättning element i dimensionen Dim som tillåts av Filter. </p> <p>Exempel: Sessioner[ Page="/home" av Visitor ] är antalet sessioner som tillhör en besökare som såg sidan "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifierare </p> </td> 
   <td colname="col2"> <p>Referensfilter har definierats på annat sätt i profilen. </p> <p>Exempel: Sessioner[ Broken_Session_Filter ] är antalet sessioner som tillåts av det brutna sessionsfiltret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Värde" </p> </td> 
   <td colname="col2"> <p>Tillåter det angivna elementet i dimensionen Dim. </p> <p>Exempel: Sessioner[ Page="A" ] är antalet sessioner som besökt sida A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tona ned &lt;&gt; "Value" </p> <p>Dim!= "Värde" </p> </td> 
   <td colname="col2"> <p>Tillåter alla andra element i dimensionen Dim. </p> <p>Exempel: Sessioner[ Sida&lt;&gt;"A" ] är antalet sessioner som besökt andra sidor än A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tona ned = #ordningstal </td> 
   <td colname="col2"> <p>Lägger till elementet för dimension-Dim med det angivna ordningstalet. </p> <p>Exempel: Sessioner[ Month=#0 ] är antalet sessioner under datauppsättningens första månad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tona ned &lt;&gt; #ordningstal </p> <p>Dim!= #ordningstal </p> </td> 
   <td colname="col2"> <p>Tillåter alla andra element i dimensionen Dim. </p> <p>Exempel: Sessioner[ Session_Value &lt;&gt; #0 ] är antalet sessioner med ett sessionsvärde som inte är noll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim matchar "Expr" </p> </td> 
   <td colname="col2"> <p>Tillåter elementen i dimension-Dim som matchar det angivna reguljära uttrycket. Dim får inte vara en denormal eller räkningsbar dimension. </p> <p>Exempel: Sessions[ URI matchar ".*/product/.*" ] är antalet sessioner som besökt en sida i en produktkatalog. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tona inte träffar "Exr" </p> </td> 
   <td colname="col2"> <p>Tillåter att elementen i dimension-Dim inte matchar det angivna reguljära uttrycket. Dim får inte vara en denormal eller räkningsbar dimension. </p> <p>Exempel: Sessions[ URI matchar inte ".*\.jsp" ] är antalet sessioner som besökt en sida som inte var en JSP-sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tona ned &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Lägger till elementen i dimensionen Dim med ordningstal som är mindre än elementets ordningstal "Value". Om "Värde" inte är ett dimensionselement antas det vara större än något aktuellt element i dimensionen. </p> <p>Exempel: Sessioner[ Månad &lt; "Jul"04" ] är antalet sessioner som ägde rum före juli 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tona ned &gt; "Värde" </p> </td> 
   <td colname="col2"> <p>Lägger till elementen i dimensionen Dim med ordningstal som är större än elementets ordningstal "Value". Om "Värde" inte är ett dimensionselement antas det vara större än något aktuellt element i dimensionen. </p> <p>Exempel: Sessioner[ Månad &gt; "Jul"04" ] är antalet sessioner som ägde rum efter juli 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Admits the elements of the dimension Dim with ordinal values less or equal to the ordinal value of the element "Value." Om "Värde" inte är ett dimensionselement antas det vara större än något aktuellt element i dimensionen. </p> <p>Exempel: Sessions[ Session_Number &lt;= "2" ] är antalet sessioner som var den första eller andra sessionen för en besökare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Admits the elements of the dimension Dim with ordinal values greater than or equal to the ordinal value of the element "Value." Om "Värde" inte är ett dimensionselement antas det vara större än något aktuellt element i dimensionen. </p> <p>Exempel: Sessions[ Session_Number &gt;= "5" ] är antalet sessioner som var den femte eller större sessionen för en besökare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all nedtoning </p> </td> 
   <td colname="col2"> <p>Tillåter alla element i dimensionen Dim. </p> <p>Exempel: Sessioner[ any Page_View ] är antalet sessioner med minst en sidvy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ingen toning </p> </td> 
   <td colname="col2"> <p>Tillåter element som alla Dim-objekt avvisar. </p> <p>Exempel: Sessioner[ ingen sidvy ] är antalet sessioner utan sidvy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTER) </p> </td> 
   <td colname="col2"> <p>Samma som FILTER. används för att gruppera en del av ett filteruttryck. </p> </td> 
  </tr> 
 </tbody> 
</table>
