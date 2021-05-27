---
description: Marknadsföring av din webbplats kan innebära att annonser placeras i form av bilder eller andra multimediefiler (från din webbserver) på tredjepartswebbplatser.
title: Mäta annonsintryckt
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Mäta annonsintryckt{#measuring-advertisement-impression}

Marknadsföring av din webbplats kan innebära att annonser placeras i form av bilder eller andra multimediefiler (från din webbserver) på tredjepartswebbplatser.

I sådana fall kanske du vill mäta både intrycket av annonsen i en webbläsare och den efterföljande klickningen, om en sådan inträffar, till annonsens mål-URL på webbplatsen.

Om du lägger till [!DNL Log=1] i frågesträngen för annonser i form av bilder blir det en bildförfrågan, och därmed även ett reklamintryck, som spelas in av [!DNL Sensor] i analyssyfte.

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_ic= | Värde som anger Impression Campaign | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | Värde som anger Impression Campaign Asset | v_ica=&quot;72890ab&quot; |
| v_icr= | Värde som anger Impression Campaign Referer | v_icr=&quot;http://money.cnn.com/markets/ |

Förutom att lägga till [!DNL Log=1] i bildbegäran bör en identifierare läggas till i webbadressen som leder från annonsen till målsidan på webbplatsen för att spåra annonsen som ledde fram till klickningen och spåra klickningen tillbaka till den specifika kampanjen för annonsen.

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=http://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Insamlade data </th> 
   <th colname="col2" class="entry"> Förklaring </th> 
   <th colname="col3" class="entry"> Exempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> v_c= </td> 
   <td colname="col2"> Värde som anger klickkampanjen </td> 
   <td colname="col3"> v_c="CAMPAIGN1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> Värde som betecknar klickbar kampanjresurs </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> Värde som betecknar klickningsbar kampanjreferens </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>marknader/ </p> </td> 
  </tr> 
 </tbody> 
</table>
