---
description: Funktionen för trattvisualisering innehåller funktioner för att bygga en kanal med flera dimensioner, obearbetade besökarnummer, procentandel besökare i varje steg samt separata omfång.
title: Funktioner
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
exl-id: e78dcefe-6f92-45de-9990-0beac09ad82f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# Funktioner{#funnel-features}

{{eol}}

Funktionen för trattvisualisering innehåller funktioner för att bygga en kanal med flera dimensioner, obearbetade besökarnummer, procentandel besökare i varje steg samt separata omfång.

Här är de grundläggande funktionerna i kanalvisualiseringen.

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> Första elementet </td> 
   <td colname="col2"> Första steget i processen. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> Tredje elementet </td> 
   <td colname="col2">Det tredje steget i processen. <p><p>Obs! De markerade elementen behöver inte vara från samma dimension. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> Procent för heltal </td> 
   <td colname="col2"> Procentandel som slutförde den definierade sökvägen som visas i tre omfång. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> Utfallsläsare </td> 
   <td colname="col2">Utfallspil. Högerklicka och välj <span class="uicontrol"> Lägg till sökvägsläsare</span> för att se vad andra besökare tog. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Procentutfall </td> 
   <td colname="col2">Procenttal som beskriver tre typer av utfall för användare som inte slutförde sökvägen. <p>Procentsatserna anges i tre områden: </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> Procentandel av bortfallet från steget före det här steget. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> Procentandel av utfallet från det första steget i tratten. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> Procentandel av utfallet baserat på totalt antal besökare. </p></td> 
  </tr> 
 </tbody> 
</table>

## Tratt Steps {#section-96a6732558dd4740b73541844f06d3ef}

Diskarna i en tratt representerar stegen i navigeringen, konerna representerar genomgången från ett steg till nästa och pilarna representerar utfallet. Om du klickar på en ikon markeras de användare som då faller igenom och inkluderas i det aktuella arbetsytefiltret. När du klickar på en pil markeras de besökare som faller bort.

>[!NOTE]
>
>Trattvisualiseringen har en gräns på åtta steg som kan tillämpas.

## Ytterligare funktioner {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Justera klipp och trattnivå**. Välj alternativet Tratt på menyn Visualisering. När tratten har skapats kan du högerklicka på titeln för att justera klippet och nivån till valfri mätbar nivå i systemet.

   ![](assets/funnel_path_browser_9.png)

* **Dra fler element**. Lägg till fler element i tratten genom att dra och släppa dem från tabellen Dimension till tratten med `<Ctrl>` + `<Alt>` nycklar. Du kan dra flera steg samtidigt från Dimensionen genom att markera flera objekt (med `<Ctrl>` + klicka) och sedan dra dem till Tratt-visualiseringen med `<Ctrl>` + `<Alt>` nycklar..
* **Ta bort ett steg**: Ta bort element genom att högerklicka på steget i visualiseringen och klicka på **Ja**.

   ![](assets/funnel_path_browser_4.png)

* **Ändra ordning på stegen som du har dragit till tratten**. Klicka bara på steget för att markera det och dra det till en annan plats för att ordna om stegen.
* **Öppna en sökvägsläsare**. Du kan se mer information om var kunderna faller igenom eller faller ifrån processen genom [Lägg till en sökvägsläsare](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119) -funktion.

* **Lägg till fler steg**. Du kan lägga till högst åtta steg för varje trattvisualisering.
* **Ändra måttet**. Mätvärdet kan ändras så att stegen är inventeringsbesök eller något annat mått i varje steg. Vilka alternativ som är tillgängliga varierar beroende på datauppsättning.
* **Visa i en tabellvy**. Högerklicka på titeln för att visa menyn Trattvisualisering och klicka på **[!UICONTROL Show Tabular View]**. I tabellvy kan du välja **[!UICONTROL Show Graph View]** för att återgå till grafisk representation av tratten. Om du vill öppna tabellvyn högerklickar du på titeln och väljer Visa tabellvy på menyn.

* **Jämför sekvenser**. Ett effektivt sätt att jämföra två liknande sekvenser är att visa deras två visualiseringar sida vid sida. Du kan också visa både tabellvyn och diagramvyn sida vid sida med funktionen Duplicera. Om du vill öppna högerklickar du på titeln och väljer Duplicera på menyn.
