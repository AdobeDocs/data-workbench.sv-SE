---
description: En räkningsbar dimensions element kan räknas av systemet.
solution: Analytics
title: Räknbara dimensioner
topic: Data workbench
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Räknbara dimensioner{#countable-dimensions}

En räkningsbar dimensions element kan räknas av systemet.

Räknbara dimensioner används vanligtvis för att skapa summavärden som returnerar antalet, eller summan, av alla element i dimensionen. Du kan definiera räkningsbara dimensioner för att räkna instanser som reservationsbokningar eller produktorder. Du kan till exempel definiera de räkningsbara dimensionsordningarna vars element (loggposter som motsvarar order från din onlinebutik) kan räknas. Om du vill visa antalet order i en visualisering definierar du summan för beställningarna, som kan utvärderas över en dimension eller ha filter för den.

Räknbara dimensioner kan vara överordnade av andra dimensioner eller underordnade av andra räkningsbara dimensioner.

>[!NOTE]
>
>Om du behöver en dimension som bara innehåller ett antal element bör du använda en numerisk dimension med en COUNT-åtgärd. Se [Numeriska dimensioner](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed).

Räknbara dimensioner definieras med följande parametrar:

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
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
   <td colname="col2"> Beskrivande namn på dimensionen som det visas för användaren i data workbench. Dimensionsnamnet får inte innehålla ett bindestreck (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kommentarer </td> 
   <td colname="col2"> Valfritt. Noteringar om den utökade dimensionen. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Villkor </td> 
   <td colname="col2"> De villkor under vilka indatafältet bidrar till att skapa den räkningsbara dimensionen. Om det anges begränsar ett villkor uppsättningen loggposter som är synliga för dimensionen och alla dess underordnade poster i datasetet schema. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dold </td> 
   <td colname="col2"> Avgör om dimensionen visas i gränssnittet för data workbench. Som standard är den här parametern inställd på false. Om dimensionen till exempel bara ska användas som bas för ett mätresultat, kan du ställa in den här parametern på true för att dölja dimensionen från data workbench-visningen. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nyckel </td> 
   <td colname="col2"> <p>Valfritt. Namnet på fältet som ska användas som nyckel. Om du definierar den här parametern finns det ett element i den räkningsbara dimensionen för varje kombination av ett element i den räkningsbara dimensionens överordnade element och ett distinkt värde för fältet som anges som nyckeln. </p> <p> Varje element i den räkningsbara dimensionen måste relateras till en sammanhängande uppsättning loggposter. Om loggposterna inte ordnas av nyckeln skapas därför ett element i den räkningsbara dimensionen varje gång nyckelfältet ändras. För att förhindra detta rekommenderar Adobe att du använder en unik nyckel som ligger intill varandra i tidsordning. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överordnad </td> 
   <td colname="col2"> <p>Namnet på den överordnade dimensionen. Alla räkningsbara dimensioner kan vara en överordnad dimension. Om du vill göra en dimension till den översta nivån i datasetens schema anger du parametern till "root". Den definierade dimensionen blir den räkningsbara rotdimensionen för datauppsättningen. Om du till exempel arbetar med Plats är dimensionen Visitor den räkningsbara rotdimensionen för datauppsättningen. </p> <p> <p>Obs!  Även om din räkningsbara rotdimension inte behöver kopplas till spårnings-ID:n i data, rekommenderar Adobe att du konfigurerar datamängdens räkningsbara rotdimension så att spårnings-ID-fältet (x-trackingid) används som Key. Därför kopplas varje element i roträkningsbar till ett unikt värde för x-trackingid, och alla data om varje element grupperas tillsammans. Om du vill konfigurera datauppsättningen på ett annat sätt kontaktar du Adobe. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

I det här exemplet illustreras definitionen av en räkningsbar dimension med händelsedata som samlats in från webbplatstrafiken. Den räkningsbara dimensionen räknar webbkampanjhändelser i en given session. Förutsättningen är att alla resurser för e-postkampanjer begärs från webbservern med &quot;email=&quot; som en del av cs-uri-query. I exemplet är det antal gånger som besökaren svarar på en e-postkampanj under en given session av intresse, inte det faktiska värdet i fältet cs-uri-query(email).

![](assets/cfg_Transformation_Dim_Countable.png)

I det här exemplet visas också definitionen av en räkningsbar dimension med händelsedata som samlats in från webbplatstrafiken, men det har en definierad Key-parameter. Den räkningsbara dimensionen för session använder fältet x-session som nyckel. (x-session-nyckelfältet är utdata från omformningen och har ett unikt värde för varje session.) [!DNL Sessionize] Alla unika kombinationer av ett element i besökardimensionen (det överordnade elementet) och x-session-nyckelfältet är ett element i sessionsdimensionen.

![](assets/cfg_Transformation_Dim_Countable2.png)

