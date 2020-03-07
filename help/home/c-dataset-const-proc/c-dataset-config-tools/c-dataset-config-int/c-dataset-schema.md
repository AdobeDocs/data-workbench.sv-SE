---
description: Gränssnittet Dataset Schema visar de utökade dimensionerna (räkningsbara, enkla, många-till-många, numeriska, denorala och tidsmått) som definieras i konfigurationsfilen för Transformation Dataset och relationerna mellan dessa dimensioner.
solution: Analytics
title: Datauppsättningsschema
topic: Data workbench
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Datauppsättningsschema{#dataset-schema}

Gränssnittet Dataset Schema visar de utökade dimensionerna (räkningsbara, enkla, många-till-många, numeriska, denorala och tidsmått) som definieras i konfigurationsfilen för Transformation Dataset och relationerna mellan dessa dimensioner.

Dessutom visar gränssnittet alla härledda dimensioner som du har definierat samt alla utökade dimensioner som har konfigurerats att vara dolda [!DNL Dataset Schema] .

![](assets/vis_DatasetSchema_Example.png)

I det här avsnittet beskrivs följande ämnen:

* [Så här tolkar du dimensionstypen med hjälp av gränssnittet Dataset-schema](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Visa standardvisualisering för en dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Visa en specifik visualisering för en dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Så här tolkar du dimensionstypen med hjälp av gränssnittet Dataset Schema {#section-16a0a12b11334c07bec558c0b7d260b1}

I följande tabell visas dimensionstyperna och färgerna i vilka deras namn visas i [!DNL Dataset Schema] gränssnittet. Överordnade för provdimensionerna (från exemplet ovan) noteras också.

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensionstyp </th> 
   <th colname="col2" class="entry"> Färg </th> 
   <th colname="col3" class="entry"> Exempeldimension och överordnad </th> 
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

## Så här visar du standardvisualisering för en dimension {#section-1bbb73a5cbb34ffb844eb1932db85318}

* Klicka på önskad dimension i [!DNL Dataset Schema] gränssnittet. Standardvisualiseringen visas. Om standardvisualiseringen till exempel är en tabell som visar sessioner och den valda dimensionen, och du klickar på URI-dimensionen, visar data workbench en tabell med URI efter sessioner.

>[!NOTE]
>
>Om du vill ändra standardvisualiseringen som visas läser du kapitlet om konfigureringsgränssnitt och analysfunktioner i *användarhandboken* för Data Workbench.

## Så här visar du en specifik visualisering för en dimension {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* Högerklicka på önskad dimension i [!DNL Dataset Schema] gränssnittet och klicka på **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
