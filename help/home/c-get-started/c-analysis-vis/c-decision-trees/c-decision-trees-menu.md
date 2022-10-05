---
description: Beslutsträd-menyn innehåller funktioner för att ställa in positiv användning, filter, alternativ för bladdistribution, förvirringsmatris och andra avancerade alternativ.
title: Alternativ för beslutsträd
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
exl-id: e139562d-4613-4159-a858-2a78a2e896dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---

# Alternativ för beslutsträd{#decision-tree-options}

{{eol}}

Beslutsträd-menyn innehåller funktioner för att ställa in positiv användning, filter, alternativ för bladdistribution, förvirringsmatris och andra avancerade alternativ.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verktygsfältsknappar </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gå </td> 
   <td colname="col2"> Klicka för att köra beslutsträdsalgoritmen och visa visualiseringen. Detta är nedtonat tills det finns indata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Återställ </td> 
   <td colname="col2"> Rensar indata och beslutsträdsmodellen och återställer processen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spara </td> 
   <td colname="col2"><b>Spara beslutsträdet</b>. Du kan spara beslutsträdet i olika format: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Predictive Markup Language (<b>PMML</b>), ett XML-baserat filformat som används av program för att beskriva och utbyta beslutsträdsmodeller. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Text</b> visa enkla kolumner och rader med true eller false, procentandelar, antal medlemmar och indatavärden. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">A <b>Dimension</b> med förgreningar som motsvarar förväntade resultatelement. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alternativ </td> 
   <td colname="col2"> Se tabellen nedan för Alternativ-menyn. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Alternativ-menyn </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ange positivt skiftläge </td> 
   <td colname="col2"> Definierar den aktuella arbetsytan som modellens positiva skiftläge. Raderar ärendet om det inte finns någon markering. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ange populationsfilter </td> 
   <td colname="col2"> Definierar den aktuella arbetsytan som modellens populationsfilter och ritas från besökare som uppfyller det här villkoret. Standardvärdet är "Alla". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visa beskrivning av komplext filter </td> 
   <td colname="col2"> Visar beskrivningar av de definierade filtren. Klicka för att visa filtreringsskripten för filtret Positivt skiftläge och Population. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dölj noder </td> 
   <td colname="col2"> Döljer noder med endast en liten andel av populationen. Det här menykommandot visas bara när beslutsträdet visas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matrix för förvrängning </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Alternativ</span> &gt; <span class="uicontrol"> Matrix för förvrängning</span> för att visa värdena Accuracy, Recall, Precision och F-Score. Ju närmare 100 procent, desto bättre blir poängen. </p> <p>Med konfusionsmatrisen får du fyra noggrannhetsvärden för modellen med en kombination av värden: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Faktiskt positivt (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Förutsedd positiv (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Verkligt negativ (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Förutsedd negativ (PN) </li> 
     </ul> </p> <p>Tips: Dessa siffror erhålls genom att använda den resulterande poängmodellen för de 20-procentiga testdata som behålls och som redan kallas det sanna svaret. Om poängen är större än 50 procent förutspås det som ett positivt skiftläge (som matchar det definierade filtret). Sedan, Accuracy = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) och Precision = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visa förklaring </td> 
   <td colname="col2">Gör att du kan aktivera och inaktivera en teckenförklaring i beslutsträdet. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Det här menykommandot visas bara när beslutsträdet visas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avancerat </td> 
   <td colname="col2"> Klicka för att öppna Avancerat-menyn för mer ingående användning av beslutsträdet. Se tabellen nedan för menyalternativ. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avancerad meny </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ange storlek för fortbildning </td> 
   <td colname="col2"> <p>Styr storleken på den utbildningsmängd som används för modellbyggnaden. Större scenbilder tar längre tid att träna, mindre scenbilder tar mindre tid. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IndatNormalisering </td> 
   <td colname="col2"> <p> Låter användaren ange om Min-Max eller Z-bakgrundstekniken ska användas för att normalisera indata i modellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMOTE-översamplingsfaktor </td> 
   <td colname="col2"> När det positiva fallet inte inträffar särskilt ofta (mindre än 10 procent) i utbildningsexemplet används SMOTE för att ge ytterligare exempel. Med det här alternativet kan användaren ange hur många fler samplingar som ska skapas med SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Distributionströskel för lövklass </td> 
   <td colname="col2"> Gör att du kan ange det tröskelvärde som antas för ett löv under trädbyggandeprocessen. Som standard måste alla medlemmar i en nod vara identiska för att det ska vara ett löv (före rensningssteget). </td> 
  </tr> 
 </tbody> 
</table>
