---
description: Tabell som visar vilka konventioner som gäller när omformningar skapas.
solution: Analytics
title: Konventioner för att konstruera omformningar
topic: Data workbench
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Konventioner för att konstruera omformningar{#conventions-for-constructing-transformations}

Tabell som visar vilka konventioner som gäller när omformningar skapas.

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Konvention </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sekventiellt utförande </td> 
   <td colname="col2"> <p>Omvandlingarna i en datauppsättningskonfigurationsfil tillämpas på loggposterna sekventiellt (det vill säga i den ordning som de listas i konfigurationsfilen). Därför måste omformningar listas i den ordning som deras utdata används som indata till andra omformningar. Mer specifikt, om utdata från en omformning används som indata till en annan omformning, är det viktigt att den tidigare omformningen listas före den senare omformningen i datauppsättningens konfigurationsfiler. Annars genererar data workbench-servern ett fel. </p> <p> Bearbetningsfaserna är ett sätt att ordna omformningar som är definierade i flera datauppsättningar, inklusive filer. För alla datauppsättningar omfattar filer som är kopplade till en viss bearbetningsfas, ordnas omformningarna baserat på deras indata och utdata. Om flera datauppsättningar dessutom innehåller filer i en scens utdata till samma fält som ett resultat av en omvandling, genererar data workbench-servern ett fel. </p> <p> Mer information om faser finns i <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Loggbearbetning av konfigurationsfil</a>, <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> Transformation Configuration File</a>och <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Dataset Include Files</a>. </p> <p>En <span class="wintitle"> Transformation Dependency Map</span> kan visa hur ett fält ändras av en serie omformningar. Se <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"> Verktyg</a>för datauppsättningskonfiguration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdatanamn </td> 
   <td colname="col2"> De flesta omformningar anger ett utdatafält. Om utdata är ett användardefinierat utökat fält måste fältets namn börja med "x-". Namn på utdatafält får inte innehålla blanksteg eller specialtecken. Namnen på utökade fält kan skrivas med olika skiftlägen, till exempel"x-NewCampaignName" eller"x-New-Campaign-Name" för läsbarhet, men de hanteras av programmet som skiftlägeskänsliga. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indatafält </td> 
   <td colname="col2"> <p>Indatafält refererar till ett av baslinjefälten eller ett fält som skapats av användaren och som är resultatet av en tidigare omformning. Om en konstant sträng behövs kan en sträng med citattecken användas i stället för ett baslinje- eller användarskapat fält. </p> <p> En lista med några av de vanligaste datafälten som Data Workbench-servern kan behandla finns i <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> Fält</a>för händelsedatapost. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enkla strängar och vektorer för strängar </td> 
   <td colname="col2"> Alla omformningar fungerar på strängar och/eller vektorer för strängar. Enkla strängar är bokstavssekvenser av tecken. Strängvektorer innehåller noll eller flera enkla strängar i en viss ordning. </td> 
  </tr> 
 </tbody> 
</table>

