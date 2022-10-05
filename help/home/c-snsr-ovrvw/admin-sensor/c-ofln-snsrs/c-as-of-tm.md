---
description: En data workbench-server blir medveten om en datakälla, till exempel en sensor, när den tar emot data från den källan.
title: Förstå"från och med"
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---

# Förstå&quot;från och med&quot;{#understanding-as-of-time}

{{eol}}

En data workbench-server blir medveten om en datakälla, till exempel en sensor, när den tar emot data från den källan.

Från och med är en garanti för att [!DNL data workbench server] har data för alla de datakällor som de är medvetna om.

Låt oss säga att vi har en uppsättning på tre [!DNL Sensors] som skickar data till [!DNL data workbench server]: WEB1, WEB2 och WEB3. Som [!DNL data workbench server] tar emot och bearbetar data från [!DNL Sensors]kommer man automatiskt att förvänta sig data från alla dessa källor. Tiden är den sista gången som [!DNL data workbench server] har tagit emot uppgifter från alla tre dessa källor.

I praktiken innebär [!DNL data workbench server] bryr sig bara om tidpunkten och inte om vad som kan kallas&quot;väggtid&quot; eller tiden från en klocka på väggen. The [!DNL data workbench server] känner till tiden endast som tidpunkten. Detta är särskilt viktigt för rapportering eftersom det garanterar att rapporter alltid körs baserat på tidpunkten, vilket garanterar att rapporter med endast partiella data aldrig kan skickas till systemets slutanvändare.

The [!DNL data workbench server] använder data som skickas från avsändaren för att tillhandahålla informationen vid tidpunkten, oavsett om det är faktiska data som samlats in från webbplatsen eller periodiska hjärtslag som skickas av [!DNL Sensors]. Dessa hjärtslag har två syften:

1. Om du vill att en beständig HTTP/1.1-anslutning ska vara öppen mellan [!DNL Sensor] och [!DNL data workbench server].

1. För att hålla tiden aktuell om webbplatstrafiken inte samlas in och skickas till [!DNL data workbench server].
