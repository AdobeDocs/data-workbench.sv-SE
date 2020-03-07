---
description: Campaign-dimensionen definieras i Site Marketing-profilen för att erbjuda funktioner för kampanjanalys.
solution: Analytics
title: Marknadsföringsprofildimensioner
topic: Data workbench
uuid: 034b4318-58e6-4638-9b13-fac83ff9f826
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Marknadsföringsprofildimensioner{#marketing-profile-dimensions}

Campaign-dimensionen definieras i Site Marketing-profilen för att erbjuda funktioner för kampanjanalys.

<table id="table_27A4B8247F6D4E18BD61041CED7D8805"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Nivå </th> 
   <th colname="col4" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campaign </td> 
   <td colname="col2"> Enkel namnändring </td> 
   <td colname="col3">Session <p>FÖRSTA ROW-åtgärden </p></td> 
   <td colname="col4"> Kampanjidentifieraren som har extraherats från ett värde i besökarens första begäran. </td> 
  </tr> 
 </tbody> 
</table>

**Exempel på mått för anpassad marknadsföringsprofil**

Du kan lägga in ytterligare datamängder för ytterligare analys. Dessa mått läggs till genom att ytterligare information läggs in i dataströmmen som samlas in för analys. Följande tabell innehåller några av de anpassade marknadsföringsdimensionerna som har lagts till i distributioner för kunder i olika branscher:

| Dimension (anpassad) | Beskrivning |
|---|---|
| Datum för e-postkampanj | Tolkar kampanjdatumet (första värdet) från frågesträngarna för e-postkampanjen. |
| Information om e-postkampanj | Samlar in värdesträngen som är kopplad till frågesträngsvariabeln för e-postkampanjer. |
| E-postkampanjsegment | Tolkar kampanjsegmentet (tredje värdet) från frågesträngarna för e-postkampanjer. |
| Typ av e-postkampanj | Tolkar kampanjtypen (andra värdet) från frågesträngarna för e-postkampanjer. |
| Information om marknadsföringskampanj | Samlar in värdesträngen som är kopplad till frågesträngsvariabler för marknadsföringskampanjer. |
| Ägare av marknadsföringskampanj | Tolkar kampanjägaren (fjärde värdet) från frågesträngarna för marknadsföringskampanjer. |
| Källa för marknadsföringskampanj | Tolkar kampanjkällan (första värde) från frågesträngar för marknadsföringskampanjer. |
| Typ av marknadsföringskampanj | Tolkar kampanjtypen (andra värdet) från frågesträngarna för marknadsföringskampanjer. |
| PPC-kampanjinformation | Samlar in värdesträngen som är kopplad till frågesträngsvariabeln ppc. |
