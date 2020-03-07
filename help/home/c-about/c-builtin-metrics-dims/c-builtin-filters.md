---
description: Profilfilter begränsar omfattningen av de data som är tillgängliga från en datauppsättning.
solution: Analytics
title: Inbyggda profilfilter
topic: Data workbench
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Inbyggda profilfilter{#built-in-profile-filters}

Profilfilter begränsar omfattningen av de data som är tillgängliga från en datauppsättning.

Förutom de filter för loggbearbetning och omformning som kan tillämpas innan eller under skapandet av en datauppsättning finns det andra profilfilter som påverkar omfattningen av de data som är tillgängliga för val från en datauppsättning. I det här avsnittet beskrivs endast den senare typen av specialfilter.

Följande profilfilter är tillgängliga för användaren när en datauppsättning har skapats:

* Filter för delmängd av data
* Sessionsfilter - brutet

>[!NOTE]
>
>Ytterligare filter kan skapas och tillämpas genom att de finns i en profils filterkatalog.

## Delning av data {#section-0defb44315d94254ab6e629ec3d6f420}

En datadelmängd fungerar som ett datafilter genom att du bara kan välja de datadimensionselement som är av intresse för dig.

Genom att skapa datadelmängder minskar du tiden som krävs för att beräkna exakta svar på dina frågor. Om den angivna datadelmängden är tillräckligt liten kan Data Workbench hämta alla data som behövs från Insight Server och snabbt och korrekt besvara frågor om delmängden. Detta är särskilt användbart om du t.ex. vet att det tar flera timmar att analysera en dag med data eller sessioner från en viss hänvisare.

Användarna kan själva skapa datadeluppsättningar eller komma åt datadeluppsättningar som definierats i en ärvd eller arbetsprofil. När en användare skapar en delmängd av datauppsättningen (genom att markera önskade data i Insight och sedan högerklicka på arbetsytan och klicka på Data > Delmängd), skapas en Data Subset.filter-fil i mappen Filter i användarprofilkatalogen. Det här filtret definierar den datadelmängd som du har markerat och sparar delmängden för framtida bruk.

>[!NOTE]
>
>Du kan skapa flera datadeluppsättningar och växla mellan dem för att visa olika delar av data. Kom ihåg att inaktivera Dela data när du vill visa alla data. I annat fall är dina mätvärden inte representativa för alla data i datauppsättningen.

## Sessionsfilter - brutet {#section-1608e97da6464b11aea27cbb7f3160e4}

Det brutna sessionsfiltret är en måttformel som enkelt kan ändras för att uppfylla alla filterkrav. I standardwebbplatsprofilerna är filtret för bruten session konfigurerat så att det omfattar alla besökare som har en synlig flagga som är inställd på 1. Värdet 1 anger att det finns en spårningscookie för besökaren.

Här följer texten i standardfilen Brutna sessioner Filter.filter som tillhandahålls av Adobe i det officiella versionspaketet för webbplatsprofilerna.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

Som standard tillämpas filtret för bruten session på arbetsytorna både på urvalet och på deras riktmärken, och du kan aktivera det genom att högerklicka på arbetsytan och klicka på Data > Brutet sessionsfilter.

Det går att referera till filtret för bruten session i filteruttryck som Broken_Session_Filter, även om det inte är aktiverat för den aktuella arbetsytan. Mer information finns i [filteruttryck](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) .
