---
description: Testresultaten måste vara tydliga och meningsfulla så att du kan vara säker på att fatta stora dollarbeslut baserat på dessa resultat.
solution: Analytics,Analytics
title: Vad ska jag testa?
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Vad ska jag testa?{#what-should-i-test}

Testresultaten måste vara tydliga och meningsfulla så att du kan vara säker på att fatta stora dollarbeslut baserat på dessa resultat.

Även om du kan testa olika sidlayouter med [!DNL Sensor] och Webbplats föreslår Adobe att du fokuserar på att testa värdefulla strategiska affärsinitiativ eller nya eller omdesignade webbplatsfunktioner som uppfyller de mål som du har ställt upp för både din webbplats och ditt företag. Du kan testa problem som de bästa prisgarantierna, personaliseringsfunktioner, marknadserbjudanden (till exempel paket eller paket), kreativ design och programprocesser.

Följande koncept är viktigast när du utvecklar ett kontrollerat experiment:

* **Förstå de rätta ändringarna.** Detta kräver viss forskning om hur er webbplats fungerar och de affärsprocesser som ligger till grund för den främre webbplatsen. Du vill göra ändringar som ger störst effekt och som enkelt kan testas.
* **Små ändringar kan få stor effekt.** Alla ändringar du testar behöver inte vara drastiska för att ha en betydande inverkan på din verksamhet. Var alltid öppen för små, men mycket viktiga ändringar.

## Metoder som stöds {#section-1071adaf54c64ba9bc5ef228c4a23635}

Många typer av experiment med många olika mål kan utföras med Site. Följande lista innehåller några exempel:

* Förbättra konverteringsgraden genom att ändra sidor, innehåll och webbplatsprocesser.
* Förändra marknadsföringskampanjer, kampanjer, merförsäljning och merförsäljning för att öka intäkterna.
* Olika sidladdningstider för att förstå kundens tjänstekvalitet och det faktiska värdet av infrastrukturprestanda.

För att uppnå dessa mål stöder Site följande typer av metoder för kontrollerad experimenterande och testning:

* **Sidersättning:** Ersätt statisk URL X med statisk URL Y. Denna metod har begränsad användning i en dynamisk miljö.
* **Dynamisk URI-ersättning:** Detta är en variant av sidersättning som ersätter statisk sida X med dynamisk sida Y för att återge dynamiskt innehåll.
* **Objektersättning:** Ersätt fast objekt X med fast objekt Y.
* **Innehållsersättning:** Ersätt innehållsuppsättningen X (flera objekt, sidor, tabeller och så vidare) med innehållsuppsättningen Y.
* **Experimentera med variabelersättning:** Ersätt JavaScript-objekt /writeCookie_X.js med JavaScript-objekt /writeCookie_Y.js här skriver du en cookie som kan användas av ett bakomliggande system för att hantera visst innehåll.

>[!NOTE]
>
>Kontrollerade experiment baseras på URI-ersättning, inte frågesträngsersättning. URI:n i en viss URL-adress markeras i följande exempel:
>
>`https://www.omniture.com/index.asp?id=1`
>
>I ditt kontrollerade experiment kan du till exempel ange att kontrollgruppens URI [!DNL index.asp] ska ersättas med testgruppens URI [!DNL index2.asp] för att avgöra vilken siddesign som ger ett större värde.
