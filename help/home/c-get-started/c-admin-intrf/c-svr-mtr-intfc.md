---
description: Gränssnittet Serverövervakaren är användbart för felsökning eller för att helt enkelt spåra prestandaparametrarna för Data Workbench-serverdatorer och rapportdatorer som är klienter för Data Workbench-serverdatorer.
solution: Analytics
title: Serverövervakarens gränssnitt
topic: Data workbench
uuid: 609dd8ea-31a9-44c1-ab75-ca783ec85650
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Serverövervakarens gränssnitt{#server-monitor-interface}

Gränssnittet Serverövervakaren är användbart för felsökning eller för att helt enkelt spåra prestandaparametrarna för Data Workbench-serverdatorer och rapportdatorer som är klienter för Data Workbench-serverdatorer.

Gränssnittet för Serverövervakaren visar antingen en grön punkt eller en röd punkt högst upp till vänster om datornamnet. En grön punkt anger att datorn fungerar utan problem. En röd punkt anger att ett eller flera fel har inträffat på datorn.

I den nedre delen av gränssnittet för Serverövervakaren visas bearbetningsstatusen för var och en av dina tillgängliga profiler samt prestandainformation om datorn.

Mer information om [!DNL Data Workbench servers]finns i *Server Products Installation and Administration Guide*. Mer information om [!DNL Report]finns i *Data Workbench Report Guide*.

**Så här öppnar du gränssnittet Serverövervakning**

* Högerklicka på noden på Data Workbench-servern eller datorn i Serverhanteraren [!DNL Report] . t

Klicka **[!UICONTROL Server Monitor]** för att visa information om en server eller klicka **[!UICONTROL Related Servers]** > **[!UICONTROL Server Monitor List]** för att visa information om ett kluster med relaterade servrar.

![](assets/vis_ServerMonitor.png)

Gränssnittet [!DNL Server Monitor]uppdateras automatiskt var 10:e sekund.

I följande tabell visas de uppgifter som kan utföras med hjälp av [!DNL Server Monitor] gränssnittet.

<table id="table_A65426669ADE44B5A6BAD9D4E99A5CAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För att utföra den här uppgiften.. </th> 
   <th colname="col2" class="entry"> Gör det här.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Kontrollera loggbearbetningsstatus för en profil </p> </td> 
   <td colname="col2"> <p>Visa <i>profilprofilnamnsvektorn</i> . I exemplet ovan skulle du visa vektorn Profile ExampleProfile för att se att ExampleProfile-processen på en server och dess loggbearbetning är 100 % slutförd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här avgör du hur lång tid det tar för datorn att svara på förfrågningar </p> </td> 
   <td colname="col2"> <p>Visa fältet för avfrågningsfördröjning. Om värdet är större än 1 000 ms kontaktar du Adobes supporttjänster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här visar du en uppskattning av hur lång tid det kan ta att slutföra omformningen eller frågan </p> </td> 
   <td colname="col2"> <p>Visa fältet för svepningstid (hh:mm:ss), som bara finns under omformning eller frågor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta reda på det aktuella antalet nätverksanslutningar till datorn </p> </td> 
   <td colname="col2"> <p>Visa den sista raden i datorns information om <span class="wintitle"> Serverövervakaren</span> . I exemplet ovan ser du att två nätverksanslutningar för närvarande kommer från en dator. </p> </td> 
  </tr> 
 </tbody> 
</table>
