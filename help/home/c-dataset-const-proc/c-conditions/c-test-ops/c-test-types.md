---
description: Villkoret Jämför och Intervall kräver att du anger vilken typ av jämförelse som ska göras för villkoret.
title: Testtyper för teståtgärder
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Testtyper för teståtgärder{#test-types-for-test-operations}

{{eol}}

Villkoret Jämför och Intervall kräver att du anger vilken typ av jämförelse som ska göras för villkoret.

I följande tabell beskrivs de tillgängliga typerna ( [!DNL LEXICAL], [!DNL NUMERIC]och [!DNL DATETIME]).

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Testtyp </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Anteckningar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> INTEGER</span> </p> </td> 
   <td colname="col2"> <p>Ändrar först inmatningsfältet till ett heltal. Om detta inte är möjligt används värdet noll. Testet returnerar bara true om det resulterande heltalsindatavärdet är större än eller lika med det angivna minimivärdet och mindre än eller lika med det angivna maxvärdet. </p> </td> 
   <td colname="col3"> <p>Om något av de minsta eller högsta fälten lämnas tomt, används rätt min- eller maxvärde som är tillgängligt för 64-bitars signerade heltal. </p> <p> Om det min- eller maxvärde som anges i villkoret inte kan tolkas till ett heltalsvärde ersätts noll och datauppsättningen avbryts inte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>Ändrar inmatningsfältet till ett datum. Om indatafältet inte kan omvandlas till ett giltigt datum returnerar villkorstestet false. Om fältet kan omvandlas till ett datum returnerar testet bara true om indatadatumet infaller på eller efter det angivna minimidatumet och på eller före det angivna maxdatumet. </p> </td> 
   <td colname="col3"> <p>Om min- och max-datumen inte är giltiga skapas inte datauppsättningen. </p> <p> Om minsta eller högsta datum inte anges ersätter systemet det minsta datumet (1 januari 1600) eller det högsta datumet (någon gång under 2400-talet). </p> <p> Adobe rekommenderar att du använder något av följande format för <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 1 januari 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 1 januari 2013 HH:MM:SS GMT </li> 
    </ul> <p> Tidszonen får standardvärdet GMT om den inte anges. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXICAL</span> </p> </td> 
   <td colname="col2"> <p>Returnerar bara true om indatafältet är lexiskt större än eller lika med den sträng som anges som minimum och mindre än eller lika med den sträng som anges i det högsta värdet. </p> </td> 
   <td colname="col3"> <p>Vid en lexikalisk jämförelse används ASCII-värdet för tecken i strängarna från vänster till höger, som jämför tecknen. För det första tecknet som inte matchar anses det som har det större ASCII-värdet vara det större av de två tecknen. Om en sträng är kortare än den andra, men fram till den punkten är alla tecken desamma, anses den längre strängen vara den större av de två. Om strängarna är tecken för teckenmotsvarighet och har exakt samma längd, anses de vara i stort sett likvärdiga. </p> </td> 
  </tr> 
 </tbody> 
</table>
