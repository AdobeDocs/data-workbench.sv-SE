---
description: Webbläsare för sökvägar kan konfigureras för att fungera med valfri kombination av grunddimension, gruppdimension, nivådimension och mätvärden som passar ditt program och din datauppsättning.
title: Konfigurera en sökvägsläsare
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Konfigurera en sökvägsläsare{#configure-a-path-browser}

{{eol}}

Webbläsare för sökvägar kan konfigureras för att fungera med valfri kombination av grunddimension, gruppdimension, nivådimension och mätvärden som passar ditt program och din datauppsättning.

När du har konfigurerat en sökvägsläsare visas den med andra sökvägsläsare i [!DNL Add Visualization] -menyn.

1. I [!DNL Profile Manager], klicka **[!UICONTROL Menu]** och sedan klicka **[!UICONTROL Add Visualization]** och **[!UICONTROL Path Browser]**.

   Minst en [!DNL *.vw] filen finns i katalogen Path Browser.

1. Högerklicka på bockmarkeringen för den önskade filen och klicka på **[!UICONTROL Make Local]**.
1. Högerklicka på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Redigera filens parametrar med följande exempelfil och tabell som stödlinjer:

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För den här parametern.. </th> 
   <th colname="col2" class="entry"> Ange den här informationen... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Basdimensionsnamn</i> </p> </td> 
   <td colname="col2"> <p>Namnet på dimensionen vars element visas i sökvägsläsaren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Gruppdimensionsnamn</i> </p> </td> 
   <td colname="col2"> <p>Namnet på dimensionen som bestämmer hur elementen i nivådimensionen grupperas för att bilda banorna i en sökvägsläsare. De nivådimensionselement som är kopplade till en enskild sökväg i en sökvägsläsare kan inte omfatta mer än ett element i en gruppdimension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Namn på nivådimension</i> </p> </td> 
   <td colname="col2"> <p>Namnet på nivån (överordnad) för basdimensionen vars element du drar till sökvägsläsaren. När du följer en bana från ett basdimensionselement till nästa, går du från ett nivådimensionselement till nästa. När du väljer en sökväg för basdimensionselement, väljer du data för motsvarande element i nivådimensionen. Markeringen innehåller alltid de element i nivådimensionen som relaterar till roten, och den förfinas genom att fler element läggs till i banan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Måttnamn</i> </p> </td> 
   <td colname="col2"> <p>Namnet på måttet vars värde för ett givet element är proportionerligt till tjockleken på banan som leder till det elementet. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Mer information om basdimension, gruppdimension, nivådimension och mått för en sökvägsläsare finns i [Sökvägsläsare](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. I Anteckningar klickar du på **[!UICONTROL File]** > **[!UICONTROL Save As]** att spara filen med ett nytt namn som baseras på gruppdimensionen, det vill säga *Gruppdimensionsnamn*.vw.

   Se till att du sparar filen i katalogen Sökväg.

   >[!NOTE]
   >
   >Så här ser du till att din sökvägsläsare sparas som en [!DNL *.vw] -filen, i [!DNL Save As] anger du Spara som typ till Alla filer.

1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
