---
description: Sensor automatiserar inhämtningen av data från din internetkanal genom att göra sig av med den större delen av det mänskliga arbete som traditionellt används i datainsamlingen.
title: Hur fungerar datainsamlingsprocessen?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Hur fungerar datainsamlingsprocessen?{#how-does-the-data-collection-process-work}

{{eol}}

Sensor automatiserar inhämtningen av data från din internetkanal genom att göra sig av med den större delen av det mänskliga arbete som traditionellt används i datainsamlingen.

I många fall använder du [!DNL Sensor] kan avsevärt förenkla datahanteringsprocessen.

Dagens stora webbplatser för Internet, extranät och intranät kan ofta köras på en mängd olika webbservrar. Loggar och data som skapas kan vara mycket stora och krångliga att hantera. Om webbplatsen till exempel har 30 webbservrar kan en av dina anställda (eller en av tjänsteleverantörens anställda) hämta och konsolidera varje loggfil på var och en av de 30 servrarna och sedan köra rapporter på dem. Installerar [!DNL Sensor] på alla dina webbservrar automatiserar hela processen, vilket minskar kostnaderna och gör data tillgängliga i realtid.

Om du vill automatisera den här processen [!DNL Sensor] samlar in råinformation om trafiken på en webbplats direkt från varje webbserver. rådata som [!DNL Sensor] hämtningar kallas händelsedata och liknar den typ av data som webbservern registrerar i sina loggfiler.

För att hämta in dessa data, instrumentera i [!DNL Sensor] registrerar information om varje HTTP-begäran som webbservern bearbetar. [!DNL Sensor] buffrar sedan informationen för att skydda den mot nätverksfel och överför på ett säkert sätt informationen via HTTP/S till [!DNL data workbench server] som du anger.

Efter [!DNL data workbench server] tar emot data, bearbetar och lagrar loggfilerna i komprimerat format [!DNL .vsl] formatera filer, så att du enkelt kan underhålla mycket stora mängder data på billig maskinvara.

Mer information om händelsedatafält som samlats in av [!DNL Sensor] in [!DNL .vsl] filer, se [Fält för händelsedatapost](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
