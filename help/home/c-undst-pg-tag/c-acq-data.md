---
description: Med sensorn kan du hämta data för webbförfrågningar (händelse- eller loggdata) samt utökade mätdata.
title: Vilken typ av data kan jag få?
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Vilken typ av data kan jag få?{#what-kind-of-data-can-i-acquire}

{{eol}}

Med sensorn kan du hämta data för webbförfrågningar (händelse- eller loggdata) samt utökade mätdata.

Utökade mätdata är inte tillgängliga för webbservrarna som en del av deras normala drift.

Följande ämnen beskrivs:

## Webbbegärandedata {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] gör det möjligt att hämta och automatiskt transportera data från webbförfrågningar (händelse- eller loggdata) till en central plats för lagring och bearbetning för analys. Såvida du inte uttryckligen väljer att filtrera bort vissa typer av förfrågningar och inte samlar in data om dessa typer av förfrågningar, [!DNL Sensor] samlar in data om alla GET-begäranden som görs av de webbservrar där den är installerad.

[!DNL Sensor] automatiserar den här datainsamlingsprocessen för alla förfrågningar om GET som görs på dina servrar och har betydande affärsfördelar och tekniska fördelar jämfört med alternativa metoder för att hämta data från webbplatsförfrågningar. Några av fördelarna:

* Begäranden som inte behövs för analys och rapportering kan filtreras bort innan ni ådrar er kostnader för deras förvärv, transport, lagring och bearbetning.
* Webbplatsadministratörer behöver inte rotera loggfiler gruppvis, antingen manuellt eller via skript.
* [!DNL Sensor] samlar ihop loggfiler på en central plats så att de blir enkla att hantera.
* [!DNL Sensor] organiserar och lagrar loggfiler i ett gemensamt databevarande format, vilket eliminerar behovet av att förbearbeta dem innan de kan användas för analys och rapportering.
* Förekomster av vissa innehållstyper kan inkluderas i loggfilerna även om de flesta förfrågningar för en viss innehållstyp automatiskt filtreras bort.
* [!DNL Sensor] komprimerar poster i loggfiler, vilket kräver betydligt mindre lagringsutrymme, vilket minskar kostnaderna och gör att data kan hållas tillgängliga för analys under längre perioder.
* [!DNL Sensor’s] feltoleranta funktioner möjliggör system- och nätverksfel samtidigt som loggdata skickas till ett centralt arkiv.
* [!DNL Sensor] gör det möjligt att implementera kontrollerade experiment med webbinnehåll, processer och marknadsföringskampanjer.
* [!DNL Sensor] tidsstämplar loggar in i 100 nanosekunder, vilket ger nya typer av analysfunktioner.
* [!DNL Sensor] tillåter webbplatsägare att lägga till data (mått) i loggposterna efter den första implementeringen för analys och rapportering.

Mer information om att hämta utökade mätdata finns i [Hämtar baslinjemått](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Utökade mätningsdata {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] har också stöd för användning av sidtaggar (eller inbäddade objektbegäranden) för att hämta mätdata som inte är tillgängliga för webbservrarna som en del av deras normala funktion. Sidtaggar används ofta för att mäta:

* Visning av en logisk sida på en dynamisk webbplats.
* Visning av innehåll eller annonser på en tredjepartskontrollerad webbplats.
* Visning av innehåll som hanteras från en webbläsarcache eller CDN.
* Detaljerad information om besökarens webbläsare, inklusive mått som sidinläsningstid, skärmupplösning, vilka formulärfält besökaren har fyllt i osv.
* Andra data som inte skickas av webbläsare till dina webbservrar på annat sätt.

[!DNL Sensor] samlar in all information som läggs in i en GET-begäran som görs till en webbserver som körs [!DNL Sensor]. Sådana förfrågningar kan komma från inbäddade objektförfrågningar av alla slag, antingen för att enkelt mäta att en viss webbläsare har gjort en begäran vid en viss tidpunkt eller för att skicka andra mätdata till datainsamlingsströmmen så att de kan behandlas för analys- och rapporteringsändamål.

[!DNL Sensor] ger det bästa av datainhämtning på både klient- och serversidan - den förvärvar data i dina webbloggar på serversidan och samlar in data från klientsidan, tredjepartswebbplatsen eller cacheminnesökningar som utförs av inbäddade objektbegäranden. Med andra ord: [!DNL Sensor] hämtar både begärandata som normalt är kända för webbservrarna (mått på serversidan) och alla andra mätdata som samlas in med hjälp av sidtaggar (klientmått) som skickar data till webbservrar som körs [!DNL Sensor]. Sådana webbservrar kan dedikeras till att samla in mått på klientsidan, men behöver inte vara det.

Mer information om att hämta utökade mätdata finns i [Hämta utökade mått](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
