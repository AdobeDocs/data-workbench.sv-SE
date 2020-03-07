---
description: Utvärdera ett beslutsträd med alternativet Regressionsträd med nya samplings- och visualiseringsfunktioner.
title: Alternativ för regressionsträd för beslutsträd
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Alternativ för regressionsträd för beslutsträd{#regression-tree-option-for-decision-tree}

Utvärdera ett beslutsträd med alternativet Regressionsträd med nya samplings- och visualiseringsfunktioner.

Utvärdera ett beslutsträd med alternativet Regressionsträd genom att högerklicka och välja Alternativ > **Regressionsträd** i en beslutsträdsvisualisering.

**Uppdaterad Beslutsträdsbyggare**: Den nya algoritmen infördes för att bygga ett [beslutsträd](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html). Den hanterar mer allmänna data och ger en mer informativ visualisering för att förbättra precisionen i förutsägelsen.

**Förbättrad datainsamling**: Ett uppdaterat adaptivt samplingsschema gör det enklare att uppnå exaktare resultat med beslut Tree och Propensity Score.

![](assets/CART-RegressionTreeOptions.jpg)

Grönt och rött anger sant eller falskt. Färgmättnaden - som djup röd kontra ljust röd - används för att ange sannolikheten. En nod med djup röd har till exempel en mycket hög sannolikhet att vara false, medan en nod med ljusröd har en lägre sannolikhet att vara false. En nod med djupgrön är mycket trolig att vara sann.

Alla beslutsträd har olika filialbredder för att ange trafiknivån för den grenen i trädet.

I en beslutsträdsvisualisering högerklickar du och väljer Alternativ > **Regressionsträd**. När du väljer det här alternativet anges ytterligare inställningar:

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regressinställning </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Använd endast en funktion</b> </p> </td> 
   <td colname="col2"> <p>Om du väljer det här alternativet används ingen funktion mer än en gång (som det ursprungliga beslutsträdet). Om du har fem indata blir trädet inte längre än fem nivåer och trädstrukturen ser ut som ett beslutsträd (men lite mer komplicerat). Med det här alternativet kan du snabbt bygga träd genom att bara använda varje funktion en gång (som ett ursprungligt beslutsträd). Det här är en standardinställning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Inställning för regressionsträdsnivå </b> </p> </td> 
   <td colname="col2"> <p>Det här alternativet styr komplexiteten i regressionsträdet. Beroende på dina data kan du behöva skapa ett <i>fint</i> träd (med en komplicerad struktur med fler noder) för att få en mer meningsfull trädklassificering. Om du har mycket data kan ett relativt <i>grovt</i> träd (mindre komplicerat med färre trädnoder) fungera bra. </p> <p> <p>Obs! Standardinställningen är <i>Normal</i> . Det finns vissa extrema fall där inställningen <i>Normal</i> inte fungerar som den ska och inställningen <i>Grov</i> eller <i>Fin</i> kan ge en bättre bild av data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Fint</i>: Det mest komplexa trädet med de mest detaljerade rapportnivåerna och de flesta grenar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Normal</i>: Genomsnittlig granularitet och grenar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>Grovt</i>: Det minst komplexa trädet med minst definierade kategorier och färre förgreningar. </p> </td> 
  </tr> 
 </tbody> 
</table>

