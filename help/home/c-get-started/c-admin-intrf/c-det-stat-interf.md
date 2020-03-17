---
description: Gränssnittet Detaljerad status är användbart för felsökning av fel eller andra problem med Data Workbench-serverdatorer.
solution: Analytics
title: Detaljerat statusgränssnitt
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: fd3afa80250d5ae20b7758ba840fd4d436545cf2

---


# Detaljerat statusgränssnitt{#detailed-status-interface}

Gränssnittet Detaljerad status är användbart för felsökning av fel eller andra problem med Data Workbench-serverdatorer.

Detta omfattar alla profiler som körs på de datorer eller datorer som [!DNL Transform] [!DNL Report] är klienter till Data Workbench-servern. Du kan komma åt [!DNL Master Server] och [!DNL Query Server Detailed Status] använda gränssnitt via [!DNL Admin] menyn. Om du vill komma åt gränssnittet för andra datorer [!DNL Detailed Status] högerklickar du på noden på servern som du vill visa status för och klickar på [!DNL Servers Manager]**[!UICONTROL Detailed Status]**. Se [Serverhanteraren](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Mer information om Data Workbench-servern finns i *Server Products Installation and Administration Guide*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Om du vill uppdatera informationen i ett [!DNL Detailed Status] gränssnitt högerklickar du på **[!UICONTROL Detailed Status]** rubriken och klickar på **[!UICONTROL Refresh]**.

I följande tabell visas de uppgifter som kan utföras med hjälp av [!DNL Detailed Status] gränssnittet.

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För att utföra den här uppgiften.. </th> 
   <th colname="col2" class="entry"> Gör det här.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visa varje datorkomponent och dess aktuella status </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Komponentstatus</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa hur mycket minne som används på datorn </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Minnesstatus</span> &gt; <span class="uicontrol"> Läs in</span>adressutrymme. </p> <p>Mer information om övervakning av adressutrymmesbelastning finns i <i>Server Products Installation and Administration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta reda på om datorn är konfigurerad att använda växeln /3GB </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Minnesstatus</span> &gt; <span class="uicontrol"> Processadressutrymme</span>. </p> <p>Om fältet <span class="wintitle"> Totalt</span> visar mer än 300000 kB är datorn konfigurerad att använda växeln /3 GB. </p> <p>Mer information om växeln /3 GB finns i <i>Server Products Installation and Administration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka mängden diskutrymme och minne som används för att lagra varje dimension samt den som används för att lagra elementens namn </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Dimensioner</span> &gt; <span class="uicontrol"> Diskanvändning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt; </i><span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>eller Prestanda¥ &gt;Dimensioner¥ &gt;Minnesanvändning¥&lt;profilnamn¥&gt;¥. </p> <p>I fälten <span class="wintitle"> Diskanvändning</span> anges namn och mängd diskutrymme (i MB) som krävs för att lagra varje dimension. Stora diskanvändningstal kan påverka frågetiderna negativt eftersom Data Workbench-servern måste läsa igenom alla data för att slutföra relaterade frågor. Om du minskar diskanvändningen för en dimension kan det ta mindre tid att slutföra relaterade frågor. </p> <p>I fälten <span class="wintitle"> Minnesanvändning</span> anges antalet element i varje dimension samt den mängd minne som krävs för att lagra listan med elementnamn. Ett stort antal element kan påverka mängden minne som används under en fråga negativt eftersom Data Workbench-servern måste läsa igenom varje element. Om du minskar antalet element i en dimension kan det ta mindre tid att slutföra relaterade frågor. </p> <p>Exempel: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka processoranvändningen för faserna i Loggbearbetning och Omvandling </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Processoranvändning</span> &gt; <span class="uicontrol"> Loggbearbetning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span><span class="uicontrol"></span>eller Prestanda¥ &gt; CPU-användning¥ &gt;Transformation¥ &gt; &lt;profilnamn&gt;. </p> <p>Var och en av dessa fältuppsättningar ger dig processoranvändningen (i sekunder) för varje fas i Loggbearbetning och Omvandling. </p> <p>Exempel: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Den tid det tar att slutföra en fråga är vanligtvis proportionerlig till den totala storleken för alla dina dimensioner. När du har granskat storleken på varje dimension kan du utvärdera om en viss dimension är tillräckligt användbar och används tillräckligt ofta för att motivera dimensionens prestanda. Om det inte är det kan du ta bort dimensionen i <span class="wintitle"> Profilhanteraren</span>.<p>En dimension vars lista med elementnamn är för stor (d.v.s. mer än 128 MB) kan orsaka "Slut på minne"-fel även om den totala mängden adressutrymme inte ligger nära gränsen. </p> <p>Om du använder ett Data Workbench-serverkluster, men inte använder centraliserad normalisering, kan en dimension vars lista över elementnamn är stor påverka minnesbudgeten avsevärt. Mer information om centraliserad normalisering finns i konfigurationsguiden för <i>datauppsättningar</i>. Om den mängd minne som krävs för att lagra alla listor med elementnamn är större än 100 MB över alla servrar i klustret, kan du få felmeddelanden om att skicka minnesbudget har överskridits även när frågeaktiviteten är ljus. Om du till exempel har ett kluster med fyra servrar med mer än 25 MB på varje server som används för att lagra listor med elementnamn, kan det uppstå fel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka tiden för loggbearbetning och -omvandling </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Processoranvändning</span> &gt; <span class="uicontrol"> Loggbearbetning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> <span class="uicontrol"></span> <span class="uicontrol"></span> <span class="uicontrol"></span> <i><span class="uicontrol"></span></i>eller Prestanda¥ &gt; CPU-användning¥ &gt; &gt; &lt;profilnamn¥&gt;. </p> <p>Genom att granska fälten i de här avsnitten kan du identifiera filter och omformningar som kan påverka tiden för loggbearbetning och omformning negativt. Sedan kan du fatta designbeslut om enskilda filter och omformningar med långa bearbetningstider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka diskutrymmesanvändningen och öka frågefrekvensen </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Loggbearbetningsfält</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>. </p> <p>Varje radobjekt i det här avsnittet motsvarar en parameter i filen <span class="filepath"> Log Processing.cfg</span> . Genom att granska dessa fält kan du se hur mycket minne varje parameter använder. Du kan sedan fatta designbeslut för enskilda objekt som är ganska stora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bestämma förfluten tid för tidigare ombearbetning eller omformning </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Bearbetningsstatus</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> &gt; Historik <span class="uicontrol"> för</span>bearbetningsläge. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Realtid - den tid som Data Workbench-servern var tillgänglig för att skapa frågor. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Snabb inmatning - den här gången plus den snabba sammanfogningstiden är den totala tid som behövs för att bearbeta datauppsättningen. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Snabb sammanslagning - den totala tid som behövs för att omforma datauppsättningen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här diagnostiserar du problem med"aktuell tid" </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Bearbetningsstatus</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> &gt; <span class="uicontrol"> Per tid</span> &gt; <span class="uicontrol"> Källor</span>. </p> <p>Genom att granska tiden för varje källa kan du avgöra vilka källor som kan påverka det totala värdet. Sedan kan ni ta itu med problemen med just dessa källor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här beräknar du hur lång tid det tar att slutföra en pågående fråga </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Körningsmotor</span>. </p> <p>Genom att granska fältet Tid <span class="wintitle"></span> för datarepning får du en uppskattning av hur lång tid det tar för en fråga att slutföras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Om du vill visa alla profiler som är tillgängliga på den här datorn och information om deras status </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Profiler</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa replikeringsstatus </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Komponentstatus</span>. </p> <p>Kontrollera status för replikeringskomponenten. Om replikering körs visas OK. Om replikeringskomponenten har misslyckats visas ett felmeddelande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här visar du <span class="wintitle"> rapportserverns</span> status för en <span class="keyword"> rapportdator</span> som ansluter till Data Workbench-servern </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Report Server-status</span>. </p> <p>I det här avsnittet av gränssnittet för <span class="wintitle"> detaljerad status</span> finns en kopia av filen <span class="filepath"> Report Server.cfg</span> , information om antalet rapporter som körs (aktuellt segment) och information om det senaste felet (senaste felet). </p> <p>Anvisningar om hur du redigerar <span class="filepath"> Report Server.cfg</span> -filen finns i <i>Data Workbench Report Guide</i>. </p> <p> <p>Obs! Om delen <span class="wintitle"> Report Server Status</span> inte visas i gränssnittet <span class="wintitle"> Detailed Status (Detaljerad status</span> ) kan du behöva konfigurera Data Workbench-servern så att den visar <span class="wintitle"> Report Server-status</span>. Stegen finns i <i>Data Workbench Report Guide</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa minnesanvändningsinformation för Omforma </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Bearbetningsstatus</span> &gt; <span class="uicontrol"> Omforma</span>. </p> <p>Mer information om Transform finns i <i>Server Products Installation and Administration Guide</i> och <i>DataSet Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spara gränssnittet för <span class="wintitle"> detaljerad status</span> som en <span class="filepath"> *.cfg</span> -fil som kan öppnas i en textredigerare som Anteckningar eller distribueras till andra </p> </td> 
   <td colname="col2"> <p>Högerklicka på rubriken <span class="uicontrol"> Detaljerad status</span> och klicka på <span class="uicontrol"> Spara kopia som</span>. </p> <p>Obs!  <p>Högerklicka på rubriken <span class="uicontrol"> Detaljerad status</span> och klicka på <span class="uicontrol"> Spara</span> till <i>servernamn</i>/status/ fungerar inte i gränssnittet <span class="wintitle"> Detaljerad status</span> . Följande felmeddelande visas: </p> <p>Det gick inte att spara /Status/. 403 Förbjuden </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa <span class="uicontrol"> rader per</span> loggkällmått </p> </td> 
   <td colname="col2"> <p>Om mätvärdena för rader per loggkälla måste rapporteras i Detaljerad status, bör Data Workbench Administrator definiera "Loggkälla-ID" och ange ett unikt namn i Loggbearbetning.cfg för den anpassade profilen. </p> </td> 
  </tr> 
 </tbody> 
</table>

