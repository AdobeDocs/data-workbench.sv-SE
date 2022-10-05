---
description: I det här avsnittet beskrivs hur du skapar primärnycklar (spårnings-ID) för Datans Workbench datauppsättningar för schemadesign och implementering.
title: Databearbetning - Skapar primärnyckel
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
exl-id: 9937038f-d011-4946-8a5b-cc724b611ae5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Databearbetning - Skapar primärnyckel{#data-processing-building-primary-key}

{{eol}}

I det här avsnittet beskrivs hur du skapar primärnycklar (spårnings-ID) för Datans Workbench datauppsättningar för schemadesign och implementering.

## Spårnings-ID {#section-24683031044a4af49988655ccb9a45fd}

När du har läst och avkodat data i DWB (med hjälp av avkodare) är det första steget att definiera spårnings-ID och tidsstämpel. Spårnings-ID är en identifierare som unikt identifierar en kundpost. Det kan vara vilket fält som helst i flödet, t.ex. e-post-ID, socialförsäkringsnummer, cookie-ID. Fältet som ska användas som spårnings-ID bestäms av klienten under identifieringssessionen. Spårnings-ID och tidsstämpel är obligatoriska fält och måste definieras för varje post.

Vanligtvis, för onlinedata, cookie-ID (kombination av *x-visid_high* och* x-visid_low*) används som standardmekanism för unik kundidentifiering, men detta kan ändras efter kundens behov. Det datum och den tidpunkt då begäran (eller händelsen) inträffar är *x-timestamp*. Alla poster i DWB grupperas efter *trackingid* och sorteras på tidsstämpel. Obligatoriskt fält [!DNL Definitions.cfg] filen är en fil som definierar de obligatoriska fälten: *x-trackingid* och *x-timestamp*.

Obs! *x-trackingid *i DWB är ett inbyggt fält och det här namnet ska inte användas för andra fält.

**Exempel 1**: Skapar *x-trackingid* med cookie-ID (när endast onlinedata används)

Om du vill skapa *x-trackingid *i DWB med cookie-ID använder du funktionen Hash för att skapa *x-trackingid* i [!DNL foundation.cfg] fil (det är bäst att definiera spårnings-ID i [!DNL foundation.cfg] men kan definieras i andra konfigurationsfiler under [!DNL Dataset > log processing] som visas:

![](assets/dwb_impl_primary_key1.png)

**Exempel 2**: Skapar *x-trackingid* med e-post-ID (när både online- och offlinedata är tillgängliga)

Under förutsättning att både offline- och onlinedata är tillgängliga (i det här exemplet), och e-post-ID är tillgängligt i båda datakällorna. Eftersom e-post-ID:t unikt identifierar en kund används det för att skapa *x-trackingid*.

Använd funktionen Hash för att skapa *trackingId* som visas:

![](assets/dwb_impl_primary_key2.png)
