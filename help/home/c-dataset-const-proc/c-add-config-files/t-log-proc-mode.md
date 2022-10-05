---
description: Med loggbehandlingsläget i konfigurationsfilen kan du pausa databearbetningen till en datauppsättning, ange offlinekällor eller ange med vilken frekvens som data workbench-servern sparar sina tillståndsfiler.
title: Loggbehandlingsläge.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Loggbehandlingsläge.cfg{#log-processing-mode-cfg}

{{eol}}

Med loggbehandlingsläget i konfigurationsfilen kan du pausa databearbetningen till en datauppsättning, ange offlinekällor eller ange med vilken frekvens som data workbench-servern sparar sina tillståndsfiler.

Gör ändringar i [!DNL Log Processing Mode.cfg] fil, inklusive att lägga till eller ta bort källor, orsakar inte ombearbetning av data.

**Så här redigerar du filen Log Processing Mode.cfg för en datauppsättningsprofil**

1. Öppna dialogrutan [!DNL Profile Manager] och klicka **[!UICONTROL Dataset]** för att visa innehållet.

   >[!NOTE]
   >
   >Om [!DNL Log Processing Mode.cfg] filen finns inte i katalogen för den önskade profilen. Du måste kopiera filen från baskatalogen på data workbench-serverdatorn till profilens katalog.

   Mer information om hur du öppnar och arbetar med [!DNL Profile Manager,] se *Användarhandbok för Data Workbench*.

1. Högerklicka på bockmarkeringen bredvid konfigurationsfilens namn och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Konfigurationsfönstret visas.
1. Redigera parametrarna i konfigurationsfilen med följande tabell som hjälp.

   >[!NOTE]
   >
   >Vissa parametrar i [!DNL Log Processing Mode.cfg] filen har namn som innehåller [!DNL Fast Input] eller [!DNL Fast Merge]. [!DNL Fast Input]avser loggbearbetningsfasen för datauppsättningens konstruktion och svarar för ungefär hälften av den totala datauppsättningens bearbetningstid. [!DNL Fast Merge] refererar till datauppsättningens omvandlingsfas endast när den föregås av loggbearbetning. [!DNL Fast Merge] inträffar inte under omformning som beror på att en [!DNL Transformation Dataset Configuration] -fil. Gilla [!DNL Fast Input], [!DNL Fast Merge] står också för ungefär hälften av datauppsättningens bearbetningstid.

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
      <td colname="col2"> <p>En justeringsparameter som påverkar datatransformeringens effektivitet. Standardvärdet är 128000000. </p> <p> <p>Obs! Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Beslutsförhållande för snabb inmatning </td> 
      <td colname="col2"> <p>En justeringsparameter som anger förhållandet mellan totala och olästa loggbyte som systemet matar in i <span class="wintitle"> Snabb inmatning</span> läge (och senare <span class="wintitle"> Snabb sammanslagning</span>) istället för att bearbeta data i realtid. </p> <p> Standardvärdet är 200, vilket innebär att systemet anger <span class="wintitle"> Snabb inmatning</span> från realtidsläge när olästa loggdata är 1/200 av totala data. Ett högre beslutsförhållande gör att systemet går in <span class="wintitle"> Snabb inmatning</span> enklare läge, medan en lägre proportion gör det mindre troligt att det går in <span class="wintitle"> Snabb inmatning</span> läge. </p> <p> <p>Obs! Om du anger parametern till 0 förhindras systemet från att gå in <span class="wintitle"> Snabb inmatning</span> läge alls, även för inledande bearbetning. Om du ställer in parametern på 1.1 kan systemet ange <span class="wintitle"> Snabb inmatning</span> under den inledande bearbetningen men inte för efterföljande bearbetning. Adobe rekommenderar inte att du använder värden mellan 0 och 1.1. Kontakta Adobe om du vill ha mer information om hur du ställer in den här parametern. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> FIFO-byte för snabb inmatning </td> 
      <td colname="col2"> <p>En justeringsparameter som balanserar minnesanvändning och systemprestanda under databearbetning. Standardvärdet är 120000000. </p> <p> <p>Obs! Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Buffertbyte för snabb sammanslagning </td> 
      <td colname="col2"> <p>En justeringsparameter som balanserar minnesanvändning och systemprestanda under databearbetning. Standardvärdet är 128000000. </p> <p> <p>Obs! Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Offlinekällor </td> 
      <td colname="col2"> <p>Masken för offlineloggkällan. </p> <p> <b> Ange en offlinekälla</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Högerklicka <span class="uicontrol"> Offlinekällor</span>och sedan klicka <span class="uicontrol"> Lägg till ny</span> &gt; <span class="uicontrol"> Källa</span>. </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> Ange masken för loggsekvensen i parametern för den nya källan. För sensorloggkällor med filnamn i formatet YYYMMDD-<i>SENSORID</i>.vsl, masken är <i>SENSORID.SENSORID</i> är skiftlägeskänsligt. För loggfilens loggkällor är masken den sträng som extraheras av <span class="wintitle"> Maskmönster</span>. Se <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Loggfiler</a>. </li> 
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
      <td colname="col2"> <p>Mängden minne i byte som används för att lagra data som väntar på att bearbetas till datauppsättningen. Du kan behöva ändra det här värdet baserat på antalet sekunder som du anger för Realtidsfördröjning. Standardvärdet är 16000000. </p> <p> <p>Obs! Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Spara intervall (sek) </td> 
      <td colname="col2"> <p>Hur ofta data workbench-servern sparar sina tillståndsfiler. Standardvärdet är 3 600. </p> <p> <p>Obs! Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   När du redigerar [!DNL Log Processing Mode.cfg] i ett datas workbench-fönster kan du använda kortkommandon för grundläggande redigeringsfunktioner, t.ex. klipp ut (Ctrl+X), kopiera (Ctrl+C), klistra in (Ctrl+V), ångra (Ctrl+Z), göra om (Ctrl+Skift+Z), markera avsnitt (klicka+dra) och markera alla (Ctrl+a). Du kan dessutom använda kortkommandona för att kopiera och klistra in text från en konfigurationsfil ( [!DNL .cfg]) till en annan.

1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.
