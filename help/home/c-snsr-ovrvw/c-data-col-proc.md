---
description: Sensor automatiserar inhämtningen av data från din internetkanal genom att göra sig av med den större delen av det mänskliga arbete som traditionellt används i datainsamlingen.
title: Hur fungerar datainsamlingsprocessen?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Hur fungerar datainsamlingsprocessen?{#how-does-the-data-collection-process-work}

Sensor automatiserar inhämtningen av data från din internetkanal genom att göra sig av med den större delen av det mänskliga arbete som traditionellt används i datainsamlingen.

I många fall kan du förenkla datahanteringsprocessen avsevärt genom att använda [!DNL Sensor].

Dagens stora webbplatser för Internet, extranät och intranät kan ofta köras på en mängd olika webbservrar. Loggar och data som skapas kan vara mycket stora och krångliga att hantera. Om webbplatsen till exempel har 30 webbservrar kan en av dina anställda (eller en av tjänsteleverantörens anställda) hämta och konsolidera varje loggfil på var och en av de 30 servrarna och sedan köra rapporter på dem. Om du installerar [!DNL Sensor] på var och en av dina webbservrar automatiseras hela processen, vilket minskar dina utgifter och gör data tillgängliga i realtid.

För att automatisera den här processen samlar [!DNL Sensor] in råinformation om trafiken på en webbplats direkt från varje webbserver. De rådata som [!DNL Sensor] hämtar kallas händelsedata och liknar den typ av data som webbservern registrerar i sina loggfiler.

Om du vill samla in dessa data, registrerar instrumenteringen i [!DNL Sensor] information om varje HTTP-begäran som webbservern bearbetar. [!DNL Sensor] buffrar sedan informationen för att skydda den mot nätverksfel och överför på ett säkert sätt informationen via HTTP/S till den  [!DNL data workbench server] som du anger.

När [!DNL data workbench server] har tagit emot data bearbetas och lagras loggfilerna i mycket komprimerade [!DNL .vsl]-formatfiler, vilket gör att du enkelt kan underhålla mycket stora mängder data på en billig maskinvara.

Mer information om de händelsedatafält som samlats in av [!DNL Sensor] i [!DNL .vsl]-filer finns i [Fält för händelsedataposter](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
