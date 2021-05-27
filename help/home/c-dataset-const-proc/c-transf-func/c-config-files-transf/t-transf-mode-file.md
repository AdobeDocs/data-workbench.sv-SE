---
description: Med konfigurationsfilen Transform Mode.cfg kan du pausa bearbetningen av data till en datauppsättning, ange offlinekällor eller ange med vilken frekvens som data workbench-servern som kör omvandlingsfunktionen sparar sina tillståndsfiler.
title: Filen Transform Mode.cfg
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Transform Mode.cfg-filen{#the-transform-mode-cfg-file}

Med konfigurationsfilen Transform Mode.cfg kan du pausa bearbetningen av data till en datauppsättning, ange offlinekällor eller ange med vilken frekvens som data workbench-servern som kör omvandlingsfunktionen sparar sina tillståndsfiler.

Att göra ändringar i [!DNL Transform Mode.cfg]-filen, inklusive att lägga till eller ta bort källor, leder inte till ombearbetning av data.

**Så här redigerar du filen Transform Mode.cfg för en datauppsättningsprofil**

1. När du arbetar i den profil vars data du vill exportera öppnar du [!DNL Profile Manager] och klickar på **[!UICONTROL Dataset]** för att visa innehållet i katalogen.
1. Högerklicka på bockmarkeringen bredvid [!DNL Transform Mode.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Fönstret [!DNL Transform Mode.cfg] visas.
1. Redigera parametrarna i konfigurationsfilen med hjälp av följande tabell som vägledning:

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parameter </th> 
    <th colname="col2" class="entry"> Beskrivning </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Offlinekällor </td> 
    <td colname="col2"> <p>Masken för offlineloggkällan. </p> <p> Så här anger du en offlinekälla: </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Högerklicka på <span class="uicontrol"> Offlinekällor</span> och klicka på <span class="uicontrol"> Lägg till ny</span> &gt; <span class="uicontrol"> Källa</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> Ange masken för loggsekvensen i parametern för den nya källan. För sensorloggkällor med filnamn i formatet <span class="filepath"> YYYMMDD-SENSORID.vsl</span> är masken <i>SENSORID.SENSORID</i> skiftlägeskänslig. För loggfilens loggkällor är masken den sträng som extraheras av <span class="wintitle">-maskmönstret</span> (se <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> loggfiler</a>). </li> 
    </ul> <p> Om du lägger till eller tar bort källor från <span class="wintitle"> offlinekällor</span> orsakar det inte ombearbetning av datauppsättningen. </p> <p> I takt med att tidsvärdena upprätthålls för bearbetning av profilens onlinekällor. När offlinekällan är online igen återupptas bearbetningen av inkommande loggfiler för den källan. </p> <p> <p>Obs! När en källa kommer online igen bör du ta bort den från <span class="wintitle"> Offlinekällor</span>. Om du inte gör det hanterar data workbench-servern källan som en onlinekälla och uppdaterar tiden så länge som källan skickar data. Om källan kopplas från igen stoppas måtten Efter tid. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Pausad </td> 
    <td colname="col2"> Sant eller falskt. Om värdet är true bearbetas inte nya data till datauppsättningen. Standardvärdet är false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Spara intervall (sek) </td> 
    <td colname="col2"> <p>Den frekvens som data workbench-servern som omvandlingsfunktionen körs på sparar sina tillståndsfiler. Standardvärdet är 3 600. </p> <p> <p>Obs!  Du bör inte ändra det här värdet utan att rådfråga Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   När du redigerar [!DNL Transform Mode.cfg]-filen i ett data workbench-fönster kan du använda kortkommandon för grundläggande redigeringsfunktioner, som att klippa ut (Ctrl+x ), kopiera (Ctrl+C), klistra in (Ctrl+V), ångra (Ctrl+Z), göra om (Ctrl+Skift+z), markera avsnitt (klicka+dra) och markera alla (Ctrl+a). Du kan dessutom använda kortkommandona för att kopiera och klistra in text från en konfigurationsfil ( [!DNL .cfg]) till en annan.

1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. Om du vill att de lokalt gjorda ändringarna ska börja gälla högerklickar du i [!DNL Profile Manager] på bockmarkeringen för data workbench [!DNL Transform Mode.cfg] i [!DNL User]-kolumnen och klickar sedan på **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, där profilnamnet är namnet på profilen som du exporterar data för. Ombearbetningen av data börjar efter synkronisering av profilen.

   Mer information om hur du ombearbetar data för export finns i [Återbearbetning och omformning](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
