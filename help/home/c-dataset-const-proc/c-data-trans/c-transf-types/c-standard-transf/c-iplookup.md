---
description: IPLookup-omvandlingen tar IP-geolokaliserings- eller IP-geointelligensdata (som tillhandahålls av en leverantör av sådana data och konverteras till ett eget format av Adobe) och omvandlar data till geografisk information som kan användas i analyser.
title: IPLookup
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
exl-id: 3e9dba44-8d31-49af-8ce0-fecaf92edeb7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 2%

---

# IPLookup{#iplookup}

{{eol}}

IPLookup-omvandlingen tar IP-geolokaliserings- eller IP-geointelligensdata (som tillhandahålls av en leverantör av sådana data och konverteras till ett eget format av Adobe) och omvandlar data till geografisk information som kan användas i analyser.

Två [!DNL IPLookup] omvandlingar visas på menyn Lägg till ny > *Omformningstyp *:

* [!DNL IPLookup] Quova för [!DNL IP geo-location] data

* [!DNL IPLookup] Digital Envoy for [!DNL IP geo-intelligence] data

När en [!DNL IPLookup] omformning, välj lämplig omformning för [!DNL IP geo-location] eller [!DNL IP geo-intelligence] data.

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Standard </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Beskrivande namn på omformningen. Här kan du ange valfritt namn. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Anteckningar om omvandlingen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor som den här omformningen används under. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fil </td> 
   <td colname="col2"> Sökfilens sökväg och filnamn. Relativa sökvägar gäller installationskatalogen för data workbench-servern. Den här filen finns vanligtvis i katalogen Lookups i installationskatalogen för data workbench-servern. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP-adress </td> 
   <td colname="col2"> Det fält som IP-adressen ska läsas från. </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> <p>Namnen på utdatasträngarna. </p> <p> The <span class="wintitle"> IPLookup</span> Quova och <span class="wintitle"> IPLookup</span> Digital Envoy-omformningar har olika utdataparametrar. Se till att du använder rätt transformering för IP-sökdata. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet [!DNL IP geo-location] data (i sökfilen) [!DNL Quova.bin]) används för att skapa de angivna utdatafälten. Utdata (AOL, ASN, Area Code o.s.v.) kan användas för att skapa dimensioner för geografisk analys av besökstrafik.

![](assets/cfg_TransformationType_IPLookup.png)
