---
description: Nedan visas de mätvärden som ingår i den historiska övervakningsprofilen för data workbench och hur de härleds.
title: Mätvärden i Datans Workbench historiska övervakningsprofil
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 0%

---

# Mätvärden i Datans Workbench historiska övervakningsprofil{#metrics-in-the-data-workbench-historical-monitoring-profile}

Nedan visas de mätvärden som ingår i den historiska övervakningsprofilen för data workbench och hur de härleds.

| **Varningskritiska** | Summan av larmdimensionen för varje Ping. |
|---|---|
| **Varningsnedladdningar** | Summan av Alert Down-dimensionen för varje Ping. |
| **Varningar** | Summan av varningsdimensionen för varje Ping. |
| **Alla komponenter** | Antal Pings där lyckade komponentkontroller är lika med &quot;1&quot; dividerat med Pings-måttet multiplicerat med 100. |
| **Efter fördröjningsminuter** | Det här måttet är summan av minuterna för fördröjning för varje Ping, dividerat med Pings-måttet. |
| **Block** | Summan av ett för varje block. |
| **Blockera alla** | Alla block. |
| **Total kapacitet** | Kapacitetsstorleken Mått gånger 2 plus Kapacitetsradens mått, dividerat med 3. |
| **Kapacitetsrad** | Summan av procentdimensionen för kapacitetsrad för varje Ping dividerat med Pings-måttet. |
| **Kapacitetsstorlek** | Summan av procentvärdet för kapacitetsstorlek för varje Ping, dividerat med Pings-måttet. |
| **Kommunikation** | Antalet ping där Snabbkontroll lyckades matchar &quot;1&quot;, dividerat med Pings-måttet. |
| **Detaljerade kontroller sekunder** | Summan av dimensionen Detaljerad kontroll sekunder för varje Ping där ping-typen är &quot;server&quot;, dividerat med Pings-måttet. |
| **Dimension GigaBytes** | Summan av Dimension gigabyte för varje Ping, dividerat med Pings-måttet. |
| **Skiva &quot;x&quot;** | Diskmåtten beräknas genom att summan av deras diskanvändning i procent för varje Ping, dividerat med Pings-måttet. |
| **Beräknade svepningsminuter** | Detta är summan av de beräknade veckodagarna för varje Ping, dividerat med Pings-måttet, där de beräknade veckodagarna är större än noll, alla dividerat med 6. |
| **Snabb inmatning MB per minut** | Summan av megabyte för snabb inmatning per minut för varje Ping dividerat med antalet Pings när MegaBytes för snabb inmatning per minut är större än noll. |
| **Snabb inmatning** | Pingar där dimensionen för Bearbetningsläge är lika med &quot;Snabb inmatning&quot; delat med Pings. |
| **Mega-byte för snabb sammanslagning per minut** | Summan av megabyte för snabb sammanslagning per minut för varje Ping, dividerat med Pings-mått. |
| **Snabb sammanslagning** | Pingar där Bearbetningsläge är lika med&quot;snabb sammanslagning&quot; dividerat med Pings-måttet. |
| **GigaBytes-fält** | Summan av fältet Gigabytes-dimension för varje Ping dividerat med Pings-mått. |
| **Läs in** | Summan av Load Average-dimensionen för varje Ping, dividerat med Pings-måttet. |
| **Loggläsning** | Summan av Loggläsningsdimensionen för varje Ping, dividerad med Pings-måttet, alla dividerat med 10. |
| **Minnessida** | Summan av procentvärdet för minnessidfil för varje Ping, dividerat med Pings-måttet. |
| **Fysiskt minne** | Summan av måttet för fysiskt minnesprocentvärde för varje Ping, dividerat med Pings-måttet. |
| **Minnesfråga** | Summan av minnesfrågeprocenten för varje Ping, dividerat med Pings-måttet. |
| **Totalt minne GB** | Summan av de fysiska megabyte-minnesdimensionerna totalt för varje Ping, dividerat med Pings-måttet. |
| **Nätverksanslutningar** | Detta är summan av nätverksanslutningarna för varje Ping dividerat med Pings-måttet. |
| **Pings x-kapacitet, övergripande** | Pings-måttet multiplicerat med det totala värdet för kapacitet. |
| **Svarstid i millisekunder** | Summan av centisekundersdimensionen för avfrågningsfördröjning för varje Ping, dividerat med Pings-måttet, alla multiplicerat med 10. |
| **Fråga körs** | Summan av en för varje Ping där den beräknade avsvekningen är större än &quot;0&quot;, dividerat med Pings-måttet där Ping-typen är lika med &quot;server&quot;. |
| **Snabbkontrollsekunder** | Summan av antalet snabbkontrollsekunder för varje Ping där Ping-typen är lika med &quot;server&quot;, dividerat med Pings-måttet. |
| **Utdatarader** | Summan av utdatarader för varje ping dividerat med Pings-måttet, multiplicerat med 100000. |
| **Realtidsläge** | Antalet Pings där Bearbetningsläget är lika med &quot;realtid&quot;, dividerat med Pings-måttet, multiplicerat med 100. |
| **Återbearbetningsläge** | 100 minus antalet Pings där Bearbetningsläge är lika med &quot;realtid&quot; dividerat med Pings-måttet, multiplicerat med 100. |
| **Stängd** | Summan av Bearbetningsdimensionen som är installerad i profilen [Profilstatus](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64). |
| **Tillfällig DB** | Summan av det tillfälliga DB-utrymmet i procent för varje Ping, dividerat med Pings-måttet. |
| **Omformning** | Summan av omformningsprocenten för varje Ping dividerat med Pings-måttet dividerat med 10. |
