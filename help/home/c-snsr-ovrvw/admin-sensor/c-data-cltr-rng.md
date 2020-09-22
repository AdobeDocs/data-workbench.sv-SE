---
description: Kontrollera om insamlaren körs med olika metoder.
solution: Analytics
title: Bekräfta att datainsamlaren körs
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---


# Bekräfta att datainsamlaren körs{#confirming-that-the-data-collector-is-running}

Kontrollera om insamlaren körs med olika metoder.

**Rekommenderad frekvens:** Var 5-10:e minut

* [Använd platstestfunktionen i sändaren.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Kontrollera [!DNL Sensor] om du ställer in en cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Använda platstest {#section-a5a697c3252e40f184c0b662926170f2}

Ett sätt att verifiera att insamlaren körs är att aktivera funktionen Platstest i sändaren. När du aktiverar Webbplatstestning skickar sändaren regelbundet (var 60:e sekund) en GET-förfrågan till webbservern som insamlaren körs på. Om webbplatstestet inte får något svar från webbservern skriver det ett felmeddelande till syslog och skickar ett felmeddelande till [!DNL data workbench server] (som skrivs till sensorloggfilen).

Om webbplatstestet tar emot ett svar från webbservern söker programmet i köfilen efter ett paket från webbservern. Om paketet inte visas (vilket anger att insamlaren inte kördes för att hämta händelsen) skriver Site Test ett felmeddelande till syslog och skickar ett felmeddelande till Adobe (som också skrivs till sensorloggfilen).

I de begäranden som Site Test skickar till webbservern anger Site Test värdet för User-Agent till &quot; [!DNL Sensor] Test&quot;. Om du inte vill att de här förfrågningarna ska visas i datauppsättningen lägger du till&quot; [!DNL Sensor] Test&quot; User-Agent i [!DNL Baseline Robots List.txt] filen eller [!DNL Extended Robots List.txt] filen i [!DNL Lookups] mappen på [!DNL data workbench server].

**Aktivera platstestning i sändaren**

1. Leta reda på [!DNL txlogd.conf] filen på datorn där [!DNL Sensor] den körs och öppna den i en textredigerare.

1. Leta reda på raden &quot;SiteTest&quot; i [!DNL txlogd.conf] filen och konfigurera den så som visas nedan. Om din [!DNL txlogd.conf] fil inte innehåller raden &quot;SiteTest&quot; lägger du bara till raden i slutet av konfigurationsfilen.

   SiteTest http, *serverAddress*, *port*, *resurs*

   där *serverAddress* är webbserverns namn eller IP-adress är *port* serverns HTTP-lyssningsport och *resurs* är den specifika resurs som du vill att platstestet ska begära när servern testas. Observera att *resursen* kan innehålla en frågesträng.

   Exempel: SiteTest http,localhost,80,/index.jsp

   Om du vill testa flera webbservrar anger du bara flera SiteTest-rader.

## Söker efter en cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Ett annat sätt att verifiera att insamlaren körs på en webbserver är att kontrollera om [!DNL Sensor] ställer in en cookie i svaren som webbservern returnerar till klienterna. Om insamlaren fungerar returnerar webbservern en v1st-cookie.

Det går att byta namn på cookien. Om du har gjort det måste du leta efter det angivna namnet, inte v1st.

Du kan utföra den här kontrollen med ett automatiserat skript eller en övervakningsagent. Kontakta Adobe Consulting Services om du vill ha ett exempelskript eller ytterligare hjälp med den här uppgiften.
