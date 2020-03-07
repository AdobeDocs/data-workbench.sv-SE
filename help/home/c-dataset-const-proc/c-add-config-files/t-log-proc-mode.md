---
description: Med loggbehandlingsläget i konfigurationsfilen kan du pausa databearbetningen till en datauppsättning, ange offlinekällor eller ange med vilken frekvens som data workbench-servern sparar sina tillståndsfiler.
solution: Analytics
title: Loggbehandlingsläge.cfg
topic: Data workbench
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Loggbehandlingsläge.cfg{#log-processing-mode-cfg}

Med loggbehandlingsläget i konfigurationsfilen kan du pausa databearbetningen till en datauppsättning, ange offlinekällor eller ange med vilken frekvens som data workbench-servern sparar sina tillståndsfiler.

Att göra ändringar i [!DNL Log Processing Mode.cfg] filen, inklusive att lägga till eller ta bort källor, leder inte till ombearbetning av data.

**Så här redigerar du filen Log Processing Mode.cfg för en datauppsättningsprofil**

1. När du arbetar i datauppsättningsprofilen öppnar du filen [!DNL Profile Manager] och klickar **[!UICONTROL Dataset]** för att visa dess innehåll.

   >[!NOTE]
   >
   >Om [!DNL Log Processing Mode.cfg] filen inte finns i katalogen för den önskade profilen måste du kopiera den här filen från baskatalogen på data workbench-serverdatorn till profilens katalog.

   Mer information om hur du öppnar och arbetar med [!DNL Profile Manager,] filen finns i *användarhandboken* för Data Workbench.

1. Högerklicka på bockmarkeringen bredvid konfigurationsfilens namn och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Konfigurationsfönstret visas.
1. Redigera parametrarna i konfigurationsfilen med följande tabell som hjälp.

   >[!NOTE]
   >
   >Vissa parametrar i [!DNL Log Processing Mode.cfg] filen har namn som innehåller [!DNL Fast Input] eller [!DNL Fast Merge]. [!DNL Fast Input]avser loggbearbetningsfasen för datauppsättningens konstruktion och svarar för ungefär hälften av den totala datauppsättningens bearbetningstid. [!DNL Fast Merge] refererar till datauppsättningens omvandlingsfas endast när den föregås av loggbearbetning. [!DNL Fast Merge] inträffar inte under omformning som beror på att en [!DNL Transformation Dataset Configuration] fil har ändrats. Precis som [!DNL Fast Input]är [!DNL Fast Merge] den också ansvarig för ungefär hälften av datauppsättningens bearbetningstid.

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Beskrivning </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Molnbyte </td> 
      <td colname="col2"> <p>En justeringsparameter som påverkar datatransformeringens effektivitet. Standardvärdet är 128000000. </p> <p> <p>Obs!  Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Beslutsförhållande för snabb inmatning </td> 
      <td colname="col2"> <p>En justeringsparameter som anger förhållandet mellan totalt antal till olästa loggbyte där systemet försätts i <span class="wintitle"> snabbinmatningsläget</span> (och därefter <span class="wintitle"> snabb sammanslagning</span>) i stället för att data bearbetas i realtid. </p> <p> Standardvärdet är 200, vilket innebär att systemet övergår till <span class="wintitle"> läget Snabb inmatning</span> från realtidsläge när olästa loggdata är 1/200 av totala data. Ett högre beslutsförhållande gör att systemet går över i <span class="wintitle"> läget för snabb inmatning</span> enklare, medan ett lägre värde gör det mindre troligt att det går över i läget för <span class="wintitle"> snabb inmatning</span> . </p> <p> <p>Obs! Om du ställer in parametern på 0 förhindras systemet från att övergå till <span class="wintitle"> läget Snabb inmatning</span> , även för inledande bearbetning. Om du ställer in parametern på 1.1 kan systemet ange <span class="wintitle"> snabb inmatning</span> under den första bearbetningen, men inte för efterföljande bearbetning. Adobe rekommenderar inte att du använder värden mellan 0 och 1.1. Mer information om hur du ställer in den här parametern får du av Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> FIFO-byte för snabb inmatning </td> 
      <td colname="col2"> <p>En justeringsparameter som balanserar minnesanvändning och systemprestanda under databearbetning. Standardvärdet är 120000000. </p> <p> <p>Obs!  Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Buffertbyte för snabb sammanslagning </td> 
      <td colname="col2"> <p>En justeringsparameter som balanserar minnesanvändning och systemprestanda under databearbetning. Standardvärdet är 128000000. </p> <p> <p>Obs!  Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Offlinekällor </td> 
      <td colname="col2"> <p>Masken för offlineloggkällan. </p> <p> <b> Ange en offlinekälla</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Högerklicka på <span class="uicontrol"> Offlinekällor</span>och klicka sedan på <span class="uicontrol"> Lägg till ny</span> &gt; <span class="uicontrol"> Källa</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Ange masken för loggsekvensen i parametern för den nya källan. För sensorloggkällor med filnamn i formatet YYYMMDD-<i>SENSORID</i>.vsl är masken <i>SENSORID.SENSORID</i> skiftlägeskänslig. För loggfilens loggkällor är masken den sträng som extraheras av <span class="wintitle"> maskmönstret</span>. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Loggfiler</a>. </li> 
      </ul> </p> <p> Att lägga till eller ta bort källor från offlinekällor orsakar inte ombearbetning av datauppsättningen. </p> <p> I takt med att tidsvärdena upprätthålls för bearbetning av profilens onlinekällor. När offlinekällan är online igen återupptas bearbetningen av inkommande loggfiler för den källan. </p> <p> När en källa kommer online igen bör du ta bort den från offlinekällor. Om du inte gör det hanterar data workbench-servern källan som en onlinekälla och uppdaterar så länge som källan skickar data. Om källan kopplas från igen stoppas måtten Efter tid. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Pausad </td> 
      <td colname="col2"> Sant eller falskt. Om värdet är true bearbetas inte nya data till datauppsättningen. Standardvärdet är false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Realtidsfördröjning </td> 
      <td colname="col2"> Den tid i sekunder som data workbench Server väntar mellan databearbetningsintervallen i datauppsättningen. När värdet är noll försöker systemet hålla jämna steg med inkommande data i realtid. Standardvärdet är noll (0), men du kan öka värdet för att minska processorbelastningen. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> FIFO-byte i realtid </td> 
      <td colname="col2"> <p>Mängden minne i byte som används för att lagra data som väntar på att bearbetas till datauppsättningen. Du kan behöva ändra det här värdet baserat på antalet sekunder som du anger för Realtidsfördröjning. Standardvärdet är 16000000. </p> <p> <p>Obs!  Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Spara intervall (sek) </td> 
      <td colname="col2"> <p>Hur ofta data workbench-servern sparar sina tillståndsfiler. Standardvärdet är 3 600. </p> <p> <p>Obs!  Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   När du redigerar [!DNL Log Processing Mode.cfg] filen i ett datarubrikfönster kan du använda kortkommandon för grundläggande redigeringsfunktioner, till exempel klipp ut (Ctrl+x ), kopiera (Ctrl+C), klistra in (Ctrl+V), ångra (Ctrl+z ), göra om (Ctrl+Skift+z ), markera avsnitt (klicka+dra) och markera alla (Ctrl+a). Du kan dessutom använda kortkommandona för att kopiera och klistra in text från en konfigurationsfil ( [!DNL .cfg]) till en annan.

1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.
1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profiler som tillhandahålls av Adobe, eftersom dina ändringar skrivs över när du installerar uppdateringar för dessa profiler.
