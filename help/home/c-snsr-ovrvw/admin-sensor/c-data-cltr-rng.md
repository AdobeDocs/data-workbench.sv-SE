---
description: Kontrollera om insamlaren körs med olika metoder.
title: Bekräfta att datainsamlaren körs
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# Bekräfta att datainsamlaren körs{#confirming-that-the-data-collector-is-running}

{{eol}}

Kontrollera om insamlaren körs med olika metoder.

**Rekommenderad frekvens:** Var 5-10:e minut

* [Använd platstestfunktionen i sändaren.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Kontrollera om [!DNL Sensor] sätter en cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Använda platstest {#section-a5a697c3252e40f184c0b662926170f2}

Ett sätt att verifiera att insamlaren körs är att aktivera funktionen Platstest i sändaren. När du aktiverar Webbplatstestning skickar sändaren regelbundet (var 60:e sekund) en GET-förfrågan till webbservern som insamlaren körs på. Om webbplatstestet inte får något svar från webbservern skriver det ett felmeddelande till syslog och skickar ett felmeddelande till [!DNL data workbench server] (som skrivs till sensorloggfilen).

Om webbplatstestet tar emot ett svar från webbservern söker programmet i köfilen efter ett paket från webbservern. Om paketet inte visas (vilket anger att insamlaren inte kördes för att hämta händelsen) skriver Site Test ett felmeddelande till syslog och skickar ett felmeddelande till Adobe (som också skrivs till sensorloggfilen).

I de begäranden som Site Test skickar till webbservern anger Site Test värdet för User-Agent till &quot; [!DNL Sensor] Testa.&quot; Lägg till &quot; [!DNL Sensor] Test&quot; User-Agent to the [!DNL Baseline Robots List.txt] eller [!DNL Extended Robots List.txt] i [!DNL Lookups] på [!DNL data workbench server].

**Aktivera platstestning i sändaren**

1. Leta reda på [!DNL txlogd.conf] fil på datorn där [!DNL Sensor] körs och öppnas i en textredigerare.

1. I [!DNL txlogd.conf] , leta reda på raden &quot;SiteTest&quot; och konfigurera den så som visas nedan. Om [!DNL txlogd.conf] filen innehåller inte raden &quot;SiteTest&quot;, utan lägger bara till raden i slutet av konfigurationsfilen.

   SiteTest http, *serverAddress*, *port*, *resurs*

   där *serverAddress* är webbserverns namn eller IP-adress, *port* är serverns HTTP-lyssningsport, och *resurs* är den specifika resurs som du vill att platstestet ska begära när servern testas. Observera att *resurs* kan innehålla en frågesträng.

   Exempel: SiteTest http,localhost,80,/index.jsp

   Om du vill testa flera webbservrar anger du bara flera SiteTest-rader.

## Söker efter en cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Ett annat sätt att verifiera att insamlaren körs på en webbserver är att kontrollera om [!DNL Sensor] anger en cookie i svaren som webbservern återgår till klienter. Om insamlaren fungerar returnerar webbservern en v1st-cookie.

Det går att byta namn på cookien. Om du har gjort det måste du leta efter det angivna namnet, inte v1st.

Du kan utföra den här kontrollen med ett automatiserat skript eller en övervakningsagent. Kontakta Adobe Consulting Services om du vill ha ett exempelskript eller ytterligare hjälp med den här uppgiften.
