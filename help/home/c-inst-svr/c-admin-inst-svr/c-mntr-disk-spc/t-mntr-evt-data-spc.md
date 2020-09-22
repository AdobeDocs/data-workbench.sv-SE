---
description: Information om övervakning av händelsedataminne och ändring av loggkatalogen för sensordata.
solution: Analytics
title: Övervaka händelsens datautrymme
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---


# Övervaka händelsens datautrymme{#monitoring-event-data-space}

Information om övervakning av händelsedataminne och ändring av loggkatalogen för sensordata.

**Rekommenderad frekvens:** Var 5-10:e minut

[!DNL Insight Server] lagrar en loggfil per [!DNL Sensor] dag på databehandlingsenheten eller filserverenheten, beroende på din konfiguration. Storleken på loggfilerna och mängden datalagringsutrymme som krävs för dem beror på många variabler, till exempel antalet webbplatser som loggas och antalet begäranden som webbservrarna tar emot per sekund.

En typisk installation av [!DNL Insight Server] (eller ett [!DNL Insight Server] kluster) kan lagra flera terabyte data, förutsatt att den maskinvara som rekommenderas av Adobe används för [!DNL Insight Server] datorn/datorerna vid implementeringen.

Vanligtvis finns alla loggdata kvar på [!DNL Insight Server] datorn. Om det blir nödvändigt att göra mer datalagringsutrymme tillgängligt på datorn kan du flytta alla loggfiler utom den senaste dagen till en annan dator eller ett annat datalagringsmedium (zip-enhet, band osv.). När du flyttar data behöver du inte stoppa [!DNL Insight Server]det, och det påverkar inte de funktioner som finns i alla [!DNL Insights] som kan vara anslutna till [!DNL Insight Server] och arbeta med kontinuerliga data. Förutsatt att du inte bearbetar eller bearbetar om en analysdatauppsättning har du fortfarande tillgång till alla tidigare data och nya data är fortfarande tillgängliga i [!DNL Insight]. Om du bearbetar eller bearbetar om en analysdatauppsättning kan du inte komma åt data förrän bearbetningen är klar.

Som standard lagras händelsedata som skapas av [!DNL Sensor] och skickas till [!DNL Insight Server] i [!DNL Logs] mappen i [!DNL Insight Server] installationskatalogen. Konfigurationsfilen för kommunikation, [!DNL Communications.cfg], anger platsen för händelseloggfiler som läses av [!DNL Insight Server].

**Ändra loggkatalogen för[!DNL Sensor]data**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för det [!DNL Insight Server] du vill konfigurera och klicka sedan på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL Communications.cfg] katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* för [!DNL Communications.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Communications.cfg].
1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicka i [!DNL Communications.cfg] fönstret **[!UICONTROL component]** för att visa innehållet.
1. Klicka i [!DNL Communications.cfg] fönstret **[!UICONTROL Servers]** för att visa innehållet. Flera typer av servrar kan visas: Filservrar, loggningsservrar, initieringsservrar, statusservrar, skicka-servrar eller replikeringsservrar.
1. Hitta LoggingServer, där [!DNL Sensor] loggfilerna som ska bearbetas av skrivs, [!DNL Insight Server]och klicka på numret för att visa menyn.

   ![Steginformation](assets/cfg_communications_examplevalues_logging.png)

   Standardkatalogen för loggen är den [!DNL Logs] mapp som finns i [!DNL Insight Server] installationskatalogen.

1. Redigera parametern Loggkatalog så att den återspeglar loggfilernas önskade plats.

   >[!NOTE]
   >
   >Ändra inga andra parametrar för LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Flera FileServers kan listas under servernoden, så du kan behöva visa innehållet i många av dem (genom att klicka på deras nummer i [!DNL Servers] listan) för att hitta servern med en lokal sökväg till loggar som ska ändras.

1. Redigera den lokala sökvägen för att spegla den önskade platsen för [!DNL .vsl] filerna.

   >[!NOTE]
   >
   >Ändra inga andra parametrar för FileServer.

   Även om platsen för loggfilerna har ändrats i [!DNL Communications.cfg] filen kan du mappa dessa filer till loggkatalogen på [!DNL Server Files Manager] genom att ange /Logs/ som URI för FileServer.

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

