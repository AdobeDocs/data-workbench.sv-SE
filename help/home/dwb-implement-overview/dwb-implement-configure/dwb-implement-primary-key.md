---
description: I det här avsnittet beskrivs hur du skapar primärnycklar (spårnings-ID) för Data Workbench-datauppsättningar för schemadesign och implementering.
title: Databearbetning - Skapar primärnyckel
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Databearbetning - Skapar primärnyckel{#data-processing-building-primary-key}

I det här avsnittet beskrivs hur du skapar primärnycklar (spårnings-ID) för Data Workbench-datauppsättningar för schemadesign och implementering.

## Spårnings-ID {#section-24683031044a4af49988655ccb9a45fd}

När du har läst och avkodat data i DWB (med hjälp av avkodare) är det första steget att definiera spårnings-ID och tidsstämpel. Spårnings-ID är en identifierare som unikt identifierar en kundpost. Det kan vara vilket fält som helst i flödet, t.ex. e-post-ID, socialförsäkringsnummer, cookie-ID. Fältet som ska användas som spårnings-ID bestäms av klienten under identifieringssessionen. Spårnings-ID och tidsstämpel är obligatoriska fält och måste definieras för varje post.

Vanligtvis används cookie-ID (kombination av *x-visid_high* och* x-visid_low*) som standardmekanism för unik kundidentifiering för onlinedata, men detta kan ändras efter kundens behov. Det datum och den tidpunkt då begäran (eller händelsen) inträffar är *x-timestamp*. Alla poster i DWB grupperas efter *spårnings-ID* och sorteras efter tidsstämpel. Filen Obligatoriskt fält [!DNL Definitions.cfg] är en fil för loggbearbetning av datauppsättning som innehåller de obligatoriska fälten: *x-trackingid* och *x-timestamp*.

Obs! *x-trackingid *i DWB är ett inbyggt fält och det här namnet ska inte användas för andra fält.

**Exempel 1**: Skapa *x-trackingid* med cookie-id (när endast onlinedata används)

Om du vill skapa *x-trackingid *i DWB med cookie-ID använder du funktionen Hash för att skapa *x-trackingid* i [!DNL foundation.cfg] filen (det är bäst att definiera spårnings-ID i [!DNL foundation.cfg] , men det kan definieras i andra konfigurationsfiler under [!DNL Dataset > log processing] -mappen) enligt följande:

![](assets/dwb_impl_primary_key1.png)

**Exempel 2**: Skapa *x-trackingid* med e-post-ID (när både online- och offlinedata är tillgängliga)

Under förutsättning att både offline- och onlinedata är tillgängliga (i det här exemplet), och e-post-ID är tillgängligt i båda datakällorna. Eftersom e-post-ID:t unikt identifierar en kund används det för att skapa *x-trackingid*.

Använd funktionen Hash för att skapa *trackingId* enligt följande:

![](assets/dwb_impl_primary_key2.png)

