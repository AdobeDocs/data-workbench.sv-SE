---
description: Processkartor kan konfigureras så att de fungerar med valfri kombination av basdimension, gruppdimension, nivådimension och mätvärden som passar ditt program och din datamängd.
title: Konfigurera en processkarta
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Konfigurera en processkarta{#configure-a-process-map}

Processkartor kan konfigureras så att de fungerar med valfri kombination av basdimension, gruppdimension, nivådimension och mätvärden som passar ditt program och din datamängd.

När du har konfigurerat en processkarta visas den med andra processkartor i [!DNL Add Visualization menu].

1. Klicka på **[!UICONTROL Menu]** i [!DNL Profile Manager], klicka på **[!UICONTROL Add Visualization]** och klicka sedan på den typ av processkarta som du vill konfigurera (2D-metrisk karta, 2D-processkarta eller 3D-processkarta).

   Minst en [!DNL *.vw]-fil finns i katalogen.

1. Högerklicka på bockmarkeringen för den önskade filen och klicka på **[!UICONTROL Make Local]**.
1. Högerklicka på bockmarkeringen för filen i kolumnen [!DNL User] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Redigera filens parametrar med följande exempelfil och tabell som stödlinjer:

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För den här parametern.. </th> 
   <th colname="col2" class="entry"> Ange den här informationen... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Måttnamn</i> </p> </td> 
   <td colname="col2"> <p>Namnet på måttet vars värde för en viss nod är proportionerligt med nodens storlek. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Basdimensionsnamn</i> </p> </td> 
   <td colname="col2"> <p>Namnet på dimensionen vars element visas som noder på processkartan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Namn på nivådimension</i> </p> </td> 
   <td colname="col2"> <p>Namnet på nivån (överordnad) för basdimensionen vars element du drar till processkartan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Gruppdimensionsnamn</i> </p> </td> 
   <td colname="col2"> <p>Namnet på den dimension som bestämmer hur elementen i nivådimensionen grupperas för att skapa anslutningar mellan noder. En anslutning mellan två noder kan inte omfatta mer än ett element i en gruppdimension. När du gör en markering baserat på en nod i en processkarta, markerar du alla element i gruppdimensionen som involverade den noden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Måttnamn för måttmappning</i> </p> </td> 
   <td colname="col2"> <p>Den här parametern gäller endast för 2D-måttscheman. </p> <p>Namnet på det mätvärde vars värde bestämmer den vågräta positionen för noderna på kartan. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Mer information om basdimension, gruppdimension, nivådimension och mått för en processkarta finns i [Processkartor](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. I Anteckningar klickar du på **[!UICONTROL File]** > **[!UICONTROL Save As]** för att spara filen med ett nytt namn baserat på basdimensionen, d.v.s. *basdimensionsnamn*.vw.

   (Om du konfigurerar en 2D-måttkarta bör du spara filen med ett namn som baseras på metriskt namn för måttkartan, det vill säga *metriskt namn för metrisk karta*.vw.) Spara filen i rätt katalog för processkarta.

   >[!NOTE]
   >
   >Om du vill vara säker på att processkartan sparas som en [!DNL *.vw]-fil anger du Spara som typ till Alla filer i fönstret [!DNL Save As].

1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du i [!DNL Profile Manager] på bockmarkeringen för filen i kolumnen [!DNL User] och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
