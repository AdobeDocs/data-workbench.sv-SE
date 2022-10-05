---
description: Information om övervakning av händelsedataminne och ändring av loggkatalogen för sensordata.
title: Övervaka händelsens datautrymme
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---

# Övervaka händelsens datautrymme{#monitoring-event-data-space}

{{eol}}

Information om övervakning av händelsedataminne och ändring av loggkatalogen för sensordata.

**Rekommenderad frekvens:** Var 5-10:e minut

[!DNL Insight Server] lagrar en loggfil per [!DNL Sensor] per dag på databehandlingsenheten eller filserverenheten, beroende på din konfiguration. Storleken på loggfilerna och mängden datalagringsutrymme som krävs för dem beror på många variabler, till exempel antalet webbplatser som loggas och antalet begäranden som webbservrarna tar emot per sekund.

En typisk installation av [!DNL Insight Server] (eller en [!DNL Insight Server] kluster) kan lagra flera terabyte data, förutsatt att den maskinvara som rekommenderas av Adobe används för implementeringen [!DNL Insight Server] datorer.

Vanligtvis finns alla loggdata kvar på [!DNL Insight Server] dator. Om det blir nödvändigt att göra mer datalagringsutrymme tillgängligt på datorn kan du flytta alla loggfiler utom den senaste dagen till en annan dator eller ett annat datalagringsmedium (zip-enhet, band osv.). Att flytta data kräver inte att du avbryter [!DNL Insight Server]och påverkar inte de funktioner som finns i [!DNL Insights] som kan vara ansluten till [!DNL Insight Server] och arbeta med kontinuerliga data. Under förutsättning att du inte bearbetar eller bearbetar om en analysdatauppsättning har du fortfarande tillgång till alla tidigare data och nya data är fortfarande tillgängliga i [!DNL Insight]. Om du bearbetar eller bearbetar om en analysdatauppsättning kan du inte komma åt data förrän bearbetningen är klar.

Som standard genereras händelsedata av [!DNL Sensor] och skickas till [!DNL Insight Server] lagras i [!DNL Logs] i [!DNL Insight Server] installationskatalog. Konfigurationsfilen för kommunikation, [!DNL Communications.cfg]anger platsen för händelseloggfiler som läses av [!DNL Insight Server].

**Så här ändrar du loggkatalogen för [!DNL Sensor] data**

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Insight Server] du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL Communications.cfg] filen finns i den här katalogen.
1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn för [!DNL Communications.cfg] och klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Communications.cfg].
1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. I [!DNL Communications.cfg] fönster, klicka **[!UICONTROL component]** för att visa innehållet.
1. I [!DNL Communications.cfg] fönster, klicka **[!UICONTROL Servers]** för att visa innehållet. Flera typer av servrar kan visas: Filservrar, loggningsservrar, initieringsservrar, statusservrar, skicka-servrar eller replikeringsservrar.
1. Hitta LoggingServer, där [!DNL Sensor] skriver sina loggfiler som ska bearbetas av [!DNL Insight Server]och klicka på dess nummer för att visa menyn.

   ![Steginformation](assets/cfg_communications_examplevalues_logging.png)

   Standardloggkatalogen är [!DNL Logs] i [!DNL Insight Server] installationskatalog.

1. Redigera parametern Loggkatalog så att den återspeglar loggfilernas önskade plats.

   >[!NOTE]
   >
   >Ändra inga andra parametrar för LoggingServer.

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Flera FileServers kan listas under noden Servrar, så du kan behöva visa innehållet i många av dem (genom att klicka på deras nummer i [!DNL Servers] ) för att hitta servern med en lokal sökväg till loggar som ska ändras.

1. Redigera den lokala sökvägen så att den motsvarar den önskade platsen för [!DNL .vsl] filer.

   >[!NOTE]
   >
   >Ändra inga andra parametrar för FileServer.

   Platsen för loggfilerna har ändrats i [!DNL Communications.cfg] kan du mappa dessa filer till loggkatalogen i [!DNL Server Files Manager] genom att ange /Logs/ som URI för FileServer.

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL Temp] kolumn och markera **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
