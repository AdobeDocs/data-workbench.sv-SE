---
description: Sensor automatiserar inhämtningen av data från din internetkanal genom att göra sig av med den större delen av det mänskliga arbete som traditionellt används i datainsamlingen.
solution: Analytics
title: Hur fungerar datainsamlingsprocessen?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---


# Hur fungerar datainsamlingsprocessen?{#how-does-the-data-collection-process-work}

Sensor automatiserar inhämtningen av data från din internetkanal genom att göra sig av med den större delen av det mänskliga arbete som traditionellt används i datainsamlingen.

I många fall [!DNL Sensor] kan användningen avsevärt förenkla datahanteringsprocessen.

Dagens stora webbplatser för Internet, extranät och intranät kan ofta köras på en mängd olika webbservrar. Loggar och data som skapas kan vara mycket stora och krångliga att hantera. Om webbplatsen till exempel har 30 webbservrar kan en av dina anställda (eller en av tjänsteleverantörens anställda) hämta och konsolidera varje loggfil på var och en av de 30 servrarna och sedan köra rapporter på dem. Om du installerar [!DNL Sensor] på var och en av dina webbservrar automatiseras hela processen, vilket minskar kostnaderna och gör data tillgängliga i realtid.

Om du vill automatisera den här processen samlar [!DNL Sensor] in råinformation om trafiken på en webbplats direkt från varje webbserver. De rådata som [!DNL Sensor] samlas in kallas händelsedata och liknar den typ av data som webbservern registrerar i sina loggfiler.

Om du vill samla in dessa data, registrerar instrumentering inom [!DNL Sensor] information om varje HTTP-begäran som webbservern bearbetar. [!DNL Sensor] buffrar sedan informationen för att skydda den mot nätverksfel och överför på ett säkert sätt informationen via HTTP/S till den [!DNL data workbench server] som du anger.

När data har tagits emot bearbetas och lagras loggfilerna i komprimerade [!DNL data workbench server] [!DNL .vsl] format, vilket gör att du enkelt kan behålla mycket stora mängder data på en billig maskinvara.

Mer information om händelsedatafält som samlats in av [!DNL Sensor] i [!DNL .vsl] filer finns i [Händelsedatafält](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
