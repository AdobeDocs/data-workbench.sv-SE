---
description: En data workbench-server blir medveten om en datakälla, till exempel en sensor, när den tar emot data från den källan.
solution: Analytics
title: Förstå"från och med"
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# Förstå&quot;från och med&quot;{#understanding-as-of-time}

En data workbench-server blir medveten om en datakälla, till exempel en sensor, när den tar emot data från den källan.

Från och med är en garanti för att data [!DNL data workbench server] finns för alla datakällor som den är medveten om.

Låt oss säga att vi har en uppsättning på tre [!DNL Sensors] som skickar data till en [!DNL data workbench server]: WEB1, WEB2 och WEB3. När data från dessa [!DNL data workbench server] tas emot och bearbetas [!DNL Sensors]förväntar sig de automatiskt data från var och en av dessa källor. Med tiden från anger du den senaste gången som data från alla dessa tre källor [!DNL data workbench server] togs emot.

I praktiken handlar det [!DNL data workbench server] bara om&quot;Från och med&quot;-tiden&quot; och inte om&quot;väggtiden&quot; eller tiden från en klocka på väggen. Tiden [!DNL data workbench server] är den sista tidpunkten. Detta är särskilt viktigt för rapportering eftersom det garanterar att rapporter alltid körs baserat på tidpunkten, vilket garanterar att rapporter med endast partiella data aldrig kan skickas till systemets slutanvändare.

I [!DNL data workbench server] används data som skickas från avsändaren för att tillhandahålla informationen så fort som möjligt, oavsett om det är faktiska data som samlats in från webbplatsen eller periodiska hjärtslag som skickas av dig [!DNL Sensors]. Dessa hjärtslag har två syften:

1. Om du vill att en beständig HTTP/1.1-anslutning ska vara öppen mellan [!DNL Sensor] och [!DNL data workbench server].

1. Om du vill att från och med-tiden ska vara aktuell om webbplatstrafiken inte samlas in och skickas till [!DNL data workbench server].

