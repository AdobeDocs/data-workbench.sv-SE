---
description: Gränssnittet Detaljerad status är användbart för felsökning av fel eller andra problem med Data Workbench serverdatorer.
title: Detaljerat statusgränssnitt
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# Detaljerat statusgränssnitt{#detailed-status-interface}

{{eol}}

Gränssnittet Detaljerad status är användbart för felsökning av fel eller andra problem med Data Workbench serverdatorer.

Detta inkluderar alla [!DNL Transform] profiler som körs på dessa datorer, eller [!DNL Report] datorer som är Data Workbench-serverns klienter. Du kan komma åt [!DNL Master Server] och [!DNL Query Server Detailed Status] gränssnitt genom [!DNL Admin] -menyn. Så här öppnar du [!DNL Detailed Status] -gränssnitt för andra datorer, i [!DNL Servers Manager]högerklicka på noden på servern som du vill visa status för och klicka på **[!UICONTROL Detailed Status]**. Se [Serverhanteraren](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

Mer information om serverservern finns i Datan Workbench *Installations- och administrationshandbok för serverprodukter*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>Uppdatera informationen i en [!DNL Detailed Status] -gränssnitt, högerklicka på **[!UICONTROL Detailed Status]** rubrik och klicka **[!UICONTROL Refresh]**.

I följande tabell visas de uppgifter som kan utföras med [!DNL Detailed Status] gränssnitt.

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
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Komponentstatus</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa hur mycket minne som används på datorn </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Minnesstatus</span> &gt; <span class="uicontrol"> Inläsning av adressutrymme</span>. </p> <p>Mer information om övervakning av adressutrymmesinläsning finns i <i>Installations- och administrationshandbok för serverprodukter</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta reda på om datorn är konfigurerad att använda växeln /3GB </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Minnesstatus</span> &gt; <span class="uicontrol"> Processadressutrymme</span>. </p> <p>Om <span class="wintitle"> Totalt</span> visar mer än 3000000 kB. Datorn är konfigurerad att använda växeln /3GB. </p> <p>Mer information om växeln /3GB finns i <i>Installations- och administrationshandbok för serverprodukter</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka mängden diskutrymme och minne som används för att lagra varje dimension samt den som används för att lagra elementens namn </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Dimensioner</span> &gt; <span class="uicontrol"> Diskanvändning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt; </i>eller <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Dimensioner</span> &gt; <span class="uicontrol"> Minnesanvändning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>. </p> <p>The <span class="wintitle"> Diskanvändning</span> I fälten anges namn och mängd diskutrymme (i MB) som krävs för att lagra varje dimension. Stora diskanvändningstal kan påverka frågetiderna negativt eftersom Datan Workbench måste läsa igenom alla data för att slutföra relaterade frågor. Om du minskar diskanvändningen för en dimension kan det ta mindre tid att slutföra relaterade frågor. </p> <p>The <span class="wintitle"> Minnesanvändning</span> I fälten anges antalet element i varje dimension och mängden minne som krävs för att lagra listan med elementnamn. Ett stort antal element kan påverka mängden minne som används under en fråga negativt eftersom Datan Workbench måste läsa igenom varje element. Om du minskar antalet element i en dimension kan det ta mindre tid att slutföra relaterade frågor. </p> <p>Exempel: <code>+&nbsp;Performance
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
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> CPU-användning</span> &gt; <span class="uicontrol"> Loggbehandling</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> eller <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> CPU-användning</span> &gt; <span class="uicontrol"> Omformning</span> &gt; &lt;<span class="uicontrol"> profilnamn</span>&gt;. </p> <p>Var och en av dessa fältuppsättningar ger dig processoranvändningen (i sekunder) för varje fas i Loggbearbetning och Omvandling. </p> <p>Exempel: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>Den tid det tar att slutföra en fråga är vanligtvis proportionerlig till den totala storleken för alla dina dimensioner. När du har granskat storleken på varje dimension kan du utvärdera om en viss dimension är tillräckligt användbar och används tillräckligt ofta för att motivera dimensionens prestanda. Om så inte är fallet kan du ta bort dimensionen i <span class="wintitle"> Profilhanteraren</span>.<p>En dimension vars lista med elementnamn är för stor (d.v.s. mer än 128 MB) kan orsaka "Slut på minne"-fel även om den totala mängden adressutrymme inte ligger nära gränsen. </p> <p>Om du använder ett serverkluster men inte använder centraliserad normalisering kan en Data Workbench vars lista över elementnamn är stor påverka minnesbudgeten avsevärt. Mer information om centraliserad normalisering finns i <i>Konfigurationshandbok för datauppsättning</i>. Om den mängd minne som krävs för att lagra alla listor med elementnamn är större än 100 MB över alla servrar i klustret, kan du få felmeddelanden om att skicka minnesbudget har överskridits även när frågeaktiviteten är ljus. Om du till exempel har ett kluster med fyra servrar med mer än 25 MB på varje server som används för att lagra listor med elementnamn, kan det uppstå fel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka tiden för loggbearbetning och -omvandling </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> CPU-användning</span> &gt; <span class="uicontrol"> Loggbehandling</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> eller <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> CPU-användning</span> &gt; <span class="uicontrol"> Omformning</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>. </p> <p>Genom att granska fälten i de här avsnitten kan du identifiera filter och omformningar som kan påverka tiden för loggbearbetning och omformning negativt. Sedan kan du fatta designbeslut om enskilda filter och omformningar med långa bearbetningstider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Övervaka diskutrymmesanvändningen och öka frågefrekvensen </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Prestanda</span> &gt; <span class="uicontrol"> Loggbearbetningsfält</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>. </p> <p>Varje radobjekt i det här avsnittet motsvarar en parameter i <span class="filepath"> Loggbearbetning.cfg</span> -fil. Genom att granska dessa fält kan du se hur mycket minne varje parameter använder. Du kan sedan fatta designbeslut för enskilda objekt som är ganska stora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bestämma förfluten tid för tidigare ombearbetning eller omformning </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Bearbetningsstatus</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> &gt; <span class="uicontrol"> Historik för bearbetningsläge</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">Realtid - den Data Workbench som servern var tillgänglig för att skapa frågor. </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">Snabb inmatning - den här gången plus den snabba sammanfogningstiden är den totala tid som behövs för att bearbeta datauppsättningen. </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">Snabb sammanslagning - den totala tid som behövs för att omforma datauppsättningen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här diagnostiserar du problem med"aktuell tid" </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Bearbetningsstatus</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i> &gt; <span class="uicontrol"> Från och med</span> &gt; <span class="uicontrol"> Källor per</span>. </p> <p>Genom att granska tiden för varje källa kan du avgöra vilka källor som kan påverka det totala värdet. Sedan kan ni ta itu med problemen med just dessa källor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här beräknar du hur lång tid det tar att slutföra en pågående fråga </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Körningsmotor</span>. </p> <p>Granska <span class="wintitle"> Datasvettningstid</span> innehåller en uppskattning av hur lång tid det tar för en fråga att slutföras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Om du vill visa alla profiler som är tillgängliga på den här datorn och information om deras status </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Profiler</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa replikeringsstatus </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Komponentstatus</span>. </p> <p>Kontrollera status för replikeringskomponenten. Om replikering körs visas OK. Om replikeringskomponenten har misslyckats visas ett felmeddelande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa <span class="wintitle"> Rapportserver</span> status för <span class="keyword"> Rapport</span> dator som ansluter till Datan Workbench </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Status för rapportserver</span>. </p> <p>Detta avsnitt i <span class="wintitle"> Detaljerad status</span> -gränssnittet innehåller en kopia av <span class="filepath"> Report Server.cfg</span> -fil, information om antalet rapporter som körs (Aktuellt segment) och information om det senaste felet (Senaste fel). </p> <p>För steg redigerar du <span class="filepath"> Report Server.cfg</span> -filen, se <i>Data Workbench Report Guide</i>. </p> <p> <p>Obs! Om <span class="wintitle"> Status för rapportserver</span> -avsnittet visas inte i <span class="wintitle"> Detaljerad status</span> kan du behöva konfigurera Data Workbench-servern för att kunna visa <span class="wintitle"> Status för rapportserver</span>. Anvisningar om hur du gör detta finns i <i>Data Workbench Report Guide</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa minnesanvändningsinformation för Omforma </p> </td> 
   <td colname="col2"> <p>Klicka <span class="uicontrol"> Bearbetningsstatus</span> &gt; <span class="uicontrol"> Omforma</span>. </p> <p>Mer information om Omforma finns i <i>Installations- och administrationshandbok för serverprodukter</i> och <i>Konfigurationshandbok för datauppsättning</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spara <span class="wintitle"> Detaljerad status</span> gränssnitt som <span class="filepath"> *.cfg</span> som kan öppnas i en textredigerare som Anteckningar eller distribueras till andra </p> </td> 
   <td colname="col2"> <p>Högerklicka på <span class="uicontrol"> Detaljerad status</span> rubrik och klicka <span class="uicontrol"> Spara kopia som</span>. </p> <p>Obs!  <p>Högerklicka på <span class="uicontrol"> Detaljerad status</span> rubrik och klicka <span class="uicontrol"> Spara</span> till <i>servernamn</i>/Status/ fungerar inte i <span class="wintitle"> Detaljerad status</span> gränssnitt. Följande felmeddelande visas: </p> <p>Det gick inte att spara /Status/. 403 Förbjuden </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa <span class="uicontrol"> Rader per loggkälla</span> mått </p> </td> 
   <td colname="col2"> <p>Om mätvärdena för rader per loggkälla måste rapporteras i Detaljerad status bör Datans Workbench administratör definiera "Loggkälla-ID" och ange ett unikt namn i Loggbearbetning.cfg för den anpassade profilen. </p> </td> 
  </tr> 
 </tbody> 
</table>
