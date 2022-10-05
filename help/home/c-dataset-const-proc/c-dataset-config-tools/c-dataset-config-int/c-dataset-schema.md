---
description: Gränssnittet Dataset Schema visar de utökade dimensionerna (räkningsbara, enkla, många-till-många, numeriska, denorala och tidsmått) som definieras i konfigurationsfilen för Transformation Dataset och relationerna mellan dessa dimensioner.
title: Datauppsättningsschema
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---

# Datauppsättningsschema{#dataset-schema}

{{eol}}

Gränssnittet Dataset Schema visar de utökade dimensionerna (räkningsbara, enkla, många-till-många, numeriska, denorala och tidsmått) som definieras i konfigurationsfilen för Transformation Dataset och relationerna mellan dessa dimensioner.

Dessutom är [!DNL Dataset Schema] -gränssnittet visar alla härledda dimensioner som du har definierat samt alla utökade dimensioner som har konfigurerats att vara dolda.

![](assets/vis_DatasetSchema_Example.png)

I det här avsnittet beskrivs följande ämnen:

* [Så här tolkar du dimensionstypen med hjälp av gränssnittet Dataset-schema](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Visa standardvisualisering för en dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Visa en specifik visualisering för en dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Så här tolkar du Dimension-typ med datamängdsschemagränssnittet {#section-16a0a12b11334c07bec558c0b7d260b1}

I följande tabell visas dimensionstyperna och färgerna i vilka deras namn visas i [!DNL Dataset Schema] gränssnitt. Överordnade för provdimensionerna (från exemplet ovan) noteras också.

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Färg </th> 
   <th colname="col3" class="entry"> Exempel på Dimension och överordnad </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Inventerbar </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Besökare - I det här schemat är Visitor en roträkningsbar dimension. </p> <p> Session - överordnad är Visitor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormal </td> 
   <td colname="col2"> Gul </td> 
   <td colname="col3"> DenormalPage - överordnad är sidvy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Härledd </td> 
   <td colname="col2"> Blå </td> 
   <td colname="col3"> Nästa sida - överordnad är Sidvy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Många-till-många </td> 
   <td colname="col2"> Rosa och grönt (stammen från den överordnade är rosa, medan dimensionsnamnet är grönt.) </td> 
   <td colname="col3"> Sökterm - överordnad är Session. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeriskt </td> 
   <td colname="col2"> Grön </td> 
   <td colname="col3"> Exakt sidvaraktighet - överordnad är Sidvy I det här exemplet är Exakt sidvaraktighet en dold numerisk dimension. Se den dolda dimensionstypen i den här tabellen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enkel </td> 
   <td colname="col2"> Grön </td> 
   <td colname="col3"> Sida - överordnad är Sidvy . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tid </td> 
   <td colname="col2"> Grön </td> 
   <td colname="col3"> Timme - föräldern är Session. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dold </td> 
   <td colname="col2"> Dolda dimensioner är en mörkare version av rätt dimensionstypfärg. En dold numerisk dimension är till exempel mörkare, mindre ljusgrön. </td> 
   <td colname="col3"> Exakt sidvaraktighet - överordnad är sidvy. </td> 
  </tr> 
 </tbody> 
</table>

## Så här visar du standardvisualisering för en Dimension {#section-1bbb73a5cbb34ffb844eb1932db85318}

* I [!DNL Dataset Schema] klickar du på önskad dimension. Standardvisualiseringen visas. Om standardvisualiseringen till exempel är en tabell som visar sessioner och den valda dimensionen, och du klickar på URI-dimensionen, visar data workbench en tabell med URI efter sessioner.

>[!NOTE]
>
>Om du vill ändra standardvisualiseringen som visas läser du kapitlet Konfigurera gränssnitt och analysfunktioner i dialogrutan *Användarhandbok för Data Workbench*.

## Så här visar du en specifik visualisering för en Dimension {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* I [!DNL Dataset Schema] -gränssnitt, högerklicka på önskad dimension och klicka **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
