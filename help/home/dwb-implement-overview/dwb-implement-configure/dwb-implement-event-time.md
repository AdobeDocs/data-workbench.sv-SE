---
description: I det här avsnittet beskrivs hur du skapar tidsstämplar för en Data Workbench-datauppsättning.
title: Konfigurera händelsetid
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera händelsetid{#setting-up-event-time}

I det här avsnittet beskrivs hur du skapar tidsstämplar för en Data Workbench-datauppsättning.

## Förstå händelsetiden {#section-e10ef2b5b6244dc5b215836e3c77d663}

Händelsetid är det datum och den tidpunkt då begäran (eller händelsen) inträffar.

Vanligtvis används *x_hit_time_gmt* som tidsstämpelfält för onlinedata. Anropets tid kan användas som tidsstämpel för offlinedata (t.ex. callcenterdata). Detta är ett obligatoriskt fält och alla datakällor ska ha ett fält i det som kan användas som tidsstämpel. Den här informationen bör tillhandahållas av din organisation.

I DWB hämtar följande fördefinierade variabler tidsstämpeln:

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> Datum och tid (GMT) då begäran togs emot av servern. Tiden uttrycks som antalet 100 nanosekunder sedan 1 januari 1600. </p> <p>Exempel: 127710989320000000 är <i>x-timestamp</i> -värdet för 11:28:52.000000 på tisdagen den 13 september 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> i formatet YYYY-MM-DD HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> är epoktiden som representerar antalet sekunder sedan 1 januari 1970, 00:00:01. </td> 
  </tr> 
 </tbody> 
</table>

Baserat på datumfältets format används x-timestamp, x-unixtime eller x-timestring. Om inkommande data till exempel har formatet ÅÅÅÅ-MM-DD, ska x-timestring användas.

Tidsstämpeln definieras i ett av formaten och DWB genererar de andra två formaten internt. Dessutom är dessa fördefinierade DWB-fält och samma namn ska inte användas för andra fält.

## Tidszoner definierade i DWB {#section-3cdd12254342442b917376661e1d9c9f}

Om datumfältet innehåller någon av de ovannämnda tidszonerna, kommer DWB att ta hänsyn till hela raden i den aktuella tidszonen. En fil har till exempel datumet definierat som 2015-01-01 00:00:00 gmtoch en annan fil har värdet 2015-01-00:00:00 cst. Den första filens datum räknas i GMT-tidszonen medan den andra filens datum kommer att vara i CST-tidszon.

| Code | Tidszon |
|---|---|
| gmt | Greenwich Mean |
| test | Eastern Standard |
| edt | Eastern Daylight |
| cst | Central standard |
| cdt | Central, dagsljus |
| mst | Mountain Standard |
| mdt | Mountain, dagsljus |
| pst | Pacific Standard |
| pdt | Pacific, dagsljus |

>[!NOTE]
>
>DWB bearbetar bara de tidszoner som nämns ovan.

## Ange anpassade tidszoner {#section-7c351921f22b439b81c73f40d5b47536}

DWB bearbetar inte förskjutningen i tidszonen. Om du vill ta hänsyn till förskjutningen i tidszonen måste data formateras i den förskjutna tidszonen.

Exempel: Om du vill ta hänsyn till datumformatet i CST-tidszonen ska data anges i formatet YYYY-MM-DD HH:MM:SS UTC +/-HMM från klienten.

2015-10-18 05:00:00 UTC -0200

## Ange händelsetid/tidsstämpel {#section-81507080f0b44ae6b83d3650ba019812}

Baserat på datumfältets format används variabeln *x-timestamp, x-unixtime* eller *x-timestring* . I exemplet nedan används *x-unixtime eftersom* x-hit_time_gmt *kommer i Unix epoc-format* .

I DWB- [!DNL foundation.cfg] filen (eller någon annan konfigurationsfil under bearbetningsmappen för datauppsättningsloggen) använder du Kopiera-omformningen för att ange händelsetiden enligt följande:

Baserat på datumfältets format används variabeln x-timestamp, x-unixtime eller x-timestring. I exemplet nedan används x-unixtime eftersom x-hit_time_gmt kommer i unix epoc-format.

I insight foundation.cfg (eller någon annan konfiguration under datasetà-loggbehandlingens mapp) använder du Kopiera-omformningen för att ställa in händelsetiden enligt nedan: ![](assets/dwb_impl_timestamp1.png)

Om datumet i är YYY-MM-DD HH:MM:SS.mmm-format används x-timestring. ![](assets/dwb_impl_timestamp2.png)Exempel: Om datumfältet har ett annat format än det som definieras i DWB, till exempel YYY/MM/DD, formaterar du det först i ett av de tidsstämpelformat som accepteras av DWB och tilldelar det sedan till motsvarande variabel. I skärmbilden nedan konverteras datumet först till formatet YYYY-MM-DD och tilldelas sedan variabeln *x-timestring *. ![](assets/dwb_impl_timestamp3.png)

