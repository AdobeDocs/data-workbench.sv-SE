---
description: Gränssnittet Detaljerad status är användbart för felsökning av fel eller andra problem med Data Workbench serverdatorer.
title: Detaljerat statusgränssnitt
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# Detaljerat statusgränssnitt{#detailed-status-interface}

Gränssnittet Detaljerad status är användbart för felsökning av fel eller andra problem med Data Workbench serverdatorer.

Detta omfattar alla [!DNL Transform]-profiler som körs på de datorerna, eller [!DNL Report]-datorer som är Data Workbench-serverns klienter. Du kan komma åt gränssnitten [!DNL Master Server] och [!DNL Query Server Detailed Status] via menyn [!DNL Admin]. Om du vill komma åt gränssnittet [!DNL Detailed Status] för andra datorer högerklickar du i [!DNL Servers Manager] på noden på servern som du vill visa status för och klickar på **[!UICONTROL Detailed Status]**. Se [Serverhanteraren](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Mer information om serverservern finns i *Installations- och administrationshandboken för serverprodukter*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Om du vill uppdatera informationen i ett [!DNL Detailed Status]-gränssnitt högerklickar du på rubriken **[!UICONTROL Detailed Status]** och klickar på **[!UICONTROL Refresh]**.

I följande tabell visas de uppgifter som kan utföras med gränssnittet [!DNL Detailed Status].

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
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Minnesstatus</span> &gt; <span class="uicontrol"> Adressutrymmesinläsning</span>. </p> <p>Mer information om övervakning av adressutrymmesbelastning finns i <i>Installations- och administrationshandboken för serverprodukter</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta reda på om datorn är konfigurerad att använda växeln /3GB </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Minnesstatus</span> &gt; <span class="uicontrol"> Processadressutrymme</span>. </p> <p>Om fältet <span class="wintitle"> Totalt</span> visar mer än 300000 kB är datorn konfigurerad att använda växeln /3GB. </p> <p>Mer information om växeln /3GB finns i <i>handboken Installation and Administration av serverprodukter</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka mängden diskutrymme och minne som används för att lagra varje dimension samt den som används för att lagra elementens namn </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Dimensioner</span> &gt; <span class="uicontrol"> Diskanvändning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt; </i>eller <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Dimensioner</span> &gt; <span class="uicontrol"> Minnesanvändning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>. </p> <p>Fälten <span class="wintitle"> Diskanvändning</span> innehåller namn och mängd diskutrymme (i MB) som krävs för att lagra varje dimension. Stora diskanvändningstal kan påverka frågetiderna negativt eftersom Datan Workbench måste läsa igenom alla data för att slutföra relaterade frågor. Om du minskar diskanvändningen för en dimension kan det ta mindre tid att slutföra relaterade frågor. </p> <p>Fälten <span class="wintitle"> Minnesanvändning</span> innehåller antalet element i varje dimension och den mängd minne som krävs för att lagra listan med elementnamn. Ett stort antal element kan påverka mängden minne som används under en fråga negativt eftersom Datan Workbench måste läsa igenom varje element. Om du minskar antalet element i en dimension kan det ta mindre tid att slutföra relaterade frågor. </p> <p>Exempel: <code>+&nbsp;Performance
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
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> CPU-användning</span> &gt; <span class="uicontrol"> Loggbearbetning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> eller <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> CPU-användning&lt;a&lt;a1 3/&gt; &gt; <span class="uicontrol"> Omvandling</span> &gt; &lt;<span class="uicontrol"> profilnamn</span>&gt;.</span> </p> <p>Var och en av dessa fältuppsättningar ger dig processoranvändningen (i sekunder) för varje fas i Loggbearbetning och Omvandling. </p> <p>Exempel: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Den tid det tar att slutföra en fråga är vanligtvis proportionerlig till den totala storleken för alla dina dimensioner. När du har granskat storleken på varje dimension kan du utvärdera om en viss dimension är tillräckligt användbar och används tillräckligt ofta för att motivera dimensionens prestanda. Om den inte är det kan du ta bort dimensionen i <span class="wintitle"> Profile Manager</span>.<p>En dimension vars lista med elementnamn är för stor (d.v.s. mer än 128 MB) kan orsaka "Slut på minne"-fel även om den totala mängden adressutrymme inte ligger nära gränsen. </p> <p>Om du använder ett serverkluster men inte använder centraliserad normalisering kan en Data Workbench vars lista över elementnamn är stor påverka minnesbudgeten avsevärt. Mer information om centraliserad normalisering finns i <i>Konfigurationshandboken för datauppsättningar</i>. Om den mängd minne som krävs för att lagra alla listor med elementnamn är större än 100 MB över alla servrar i klustret, kan du få felmeddelanden om att skicka minnesbudget har överskridits även när frågeaktiviteten är ljus. Om du till exempel har ett kluster med fyra servrar med mer än 25 MB på varje server som används för att lagra listor med elementnamn, kan det uppstå fel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka tiden för loggbearbetning och -omvandling </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> CPU-användning</span> &gt; <span class="uicontrol"> Loggbearbetning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> eller <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> CPU-användning&lt;a&lt;a1 3/&gt; &gt; <span class="uicontrol"> Omvandling</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>.</span> </p> <p>Genom att granska fälten i de här avsnitten kan du identifiera filter och omformningar som kan påverka tiden för loggbearbetning och omformning negativt. Sedan kan du fatta designbeslut om enskilda filter och omformningar med långa bearbetningstider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka diskutrymmesanvändningen och öka frågefrekvensen </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Loggbearbetningsfält</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>. </p> <p>Varje radobjekt i det här avsnittet motsvarar en parameter i filen <span class="filepath"> Log Processing.cfg</span>. Genom att granska dessa fält kan du se hur mycket minne varje parameter använder. Du kan sedan fatta designbeslut för enskilda objekt som är ganska stora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bestämma förfluten tid för tidigare ombearbetning eller omformning </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Bearbetningsstatus</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> &gt; <span class="uicontrol"> Bearbetningslägeshistorik</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Realtid - den Data Workbench som servern var tillgänglig för att skapa frågor. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Snabb inmatning - den här gången plus den snabba sammanfogningstiden är den totala tid som behövs för att bearbeta datauppsättningen. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Snabb sammanslagning - den totala tid som behövs för att omforma datauppsättningen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här diagnostiserar du problem med"aktuell tid" </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Bearbetningsstatus</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> &gt; <span class="uicontrol"> Efter tid</span> &gt; <span class="uicontrol"> Källor efter</span>. </p> <p>Genom att granska tiden för varje källa kan du avgöra vilka källor som kan påverka det totala värdet. Sedan kan ni ta itu med problemen med just dessa källor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här beräknar du hur lång tid det tar att slutföra en pågående fråga </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Körningsmotor</span>. </p> <p>Om du granskar fältet <span class="wintitle"> Datasepningstid</span> får du en uppskattning av hur lång tid det tar för en fråga att slutföras. </p> </td> 
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
   <td colname="col1"> <p>Om du vill visa <span class="wintitle"> Report Server</span>-status för en <span class="keyword"> Report</span>-dator som ansluter till Datan Workbench </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Report Server-status</span>. </p> <p>I det här avsnittet av gränssnittet <span class="wintitle"> Detailed Status</span> finns en kopia av filen <span class="filepath"> Report Server.cfg</span>, information om antalet rapporter som körs (Aktuellt segment) och information om det senaste felet (Senaste fel). </p> <p>Anvisningar om hur du redigerar filen <span class="filepath"> Report Server.cfg</span> finns i <i>Data Workbench Report Guide</i>. </p> <p> <p>Obs! Om <span class="wintitle"> Report Server-status</span>-avsnittet inte visas i gränssnittet <span class="wintitle"> Detailed Status</span> kan du behöva konfigurera Datan Workbench så att den visar <span class="wintitle"> Report Server-status</span>. Anvisningar om hur du gör detta finns i <i>Data Workbench Report Guide</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa minnesanvändningsinformation för Omforma </p> </td> 
   <td colname="col2"> <p>Klicka på <span class="uicontrol"> Bearbetningsstatus</span> &gt; <span class="uicontrol"> Omforma</span>. </p> <p>Mer information om Transform finns i <i>handboken om installation och administration av serverprodukter</i> och <i>handboken om konfiguration av datauppsättning</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här sparar du gränssnittet <span class="wintitle"> Detailed Status</span> som en <span class="filepath"> *.cfg</span>-fil som kan öppnas i en textredigerare som Anteckningar eller distribueras till andra </p> </td> 
   <td colname="col2"> <p>Högerklicka på rubriken <span class="uicontrol"> Detaljerad status</span> och klicka på <span class="uicontrol"> Spara kopia som</span>. </p> <p>Obs!  <p>Högerklicka på rubriken <span class="uicontrol"> Detaljerad status</span> och klicka på <span class="uicontrol"> Spara</span> till <i>servernamn</i>/Status/ fungerar inte i gränssnittet <span class="wintitle"> Detaljerad status</span>. Följande felmeddelande visas: </p> <p>Det gick inte att spara /Status/. 403 Förbjuden </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa <span class="uicontrol"> rader per loggkälla</span>-mått </p> </td> 
   <td colname="col2"> <p>Om mätvärdena för rader per loggkälla måste rapporteras i Detaljerad status bör Datans Workbench administratör definiera "Loggkälla-ID" och ange ett unikt namn i Loggbearbetning.cfg för den anpassade profilen. </p> </td> 
  </tr> 
 </tbody> 
</table>
