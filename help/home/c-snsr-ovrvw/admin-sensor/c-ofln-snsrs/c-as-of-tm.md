---
description: En data workbench-server blir medveten om en datakälla, till exempel en sensor, när den tar emot data från den källan.
title: Förstå"från och med"
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---

# Tid för &quot;per&quot;{#understanding-as-of-time}

En data workbench-server blir medveten om en datakälla, till exempel en sensor, när den tar emot data från den källan.

Från och med är en garanti för att [!DNL data workbench server] har data för alla datakällor som den är medveten om.

Låt oss säga att vi har en uppsättning på tre [!DNL Sensors] som skickar data till en [!DNL data workbench server]: WEB1, WEB2 och WEB3. När [!DNL data workbench server] tar emot och bearbetar data från dessa [!DNL Sensors] förväntas automatiskt data från var och en av dessa källor. Tidsvärdet är den senaste gången som [!DNL data workbench server] tog emot data från alla tre källorna.

I praktiken bryr sig [!DNL data workbench server] bara om tiden från och med och inte om vad som kan kallas &quot;väggtid&quot; eller tiden från en klocka på väggen. [!DNL data workbench server] känner bara till tiden som tidpunkten. Detta är särskilt viktigt för rapportering eftersom det garanterar att rapporter alltid körs baserat på tidpunkten, vilket garanterar att rapporter med endast partiella data aldrig kan skickas till systemets slutanvändare.

I [!DNL data workbench server] används data som skickas från sändaren för att ge information om tidpunkten, oavsett om det är faktiska data som samlats in från webbplatsen eller periodiska hjärtslag som skickas av din [!DNL Sensors]. Dessa hjärtslag har två syften:

1. Om du vill att en beständig HTTP/1.1-anslutning ska vara öppen mellan [!DNL Sensor] och [!DNL data workbench server].

1. Om du vill att från och med-tiden ska vara aktuell om webbplatstrafiken inte samlas in och skickas till [!DNL data workbench server].
