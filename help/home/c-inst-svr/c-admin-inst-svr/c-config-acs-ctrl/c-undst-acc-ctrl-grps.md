---
description: Det finns fem fördefinierade åtkomstkontrollsgrupper, men du kan skapa och hantera ytterligare grupper efter behov.
title: Om åtkomstkontrollgrupper
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---

# Om åtkomstkontrollgrupper{#understanding-access-control-groups}

Det finns fem fördefinierade åtkomstkontrollsgrupper, men du kan skapa och hantera ytterligare grupper efter behov.

Du kan definiera medlemmarna i varje åtkomstkontrollgrupp samt katalogerna som varje grupp har skrivskyddad eller skrivskyddad åtkomst till.

De fördefinierade grupperna definieras enligt följande:

| Grupp | Beskrivning |
|---|---|
| Administratörer | Tillåter åtkomst till alla kataloger och filer. IP-standardadressen är 127.0.0.1 (lokal värd). |
| Sensorer | Tillåter endast åtkomst till de filer som används av [!DNL Sensor] för att överföra data. |
| Användare | Ger skrivskyddad åtkomst till de element som krävs för att en [!DNL Insight]-användare ska kunna utföra grundläggande analysåtgärder. |
| Avancerade användare | Ger skrivskyddad åtkomst till de element som krävs för att en [!DNL Insight]-användare ska kunna utföra grundläggande analysåtgärder, samt läs- och skrivåtkomst till mappen [!DNL Profiles] för att ändra profiler. |
| Klusterservrar | Tillåter åtkomst till [!DNL Insight Servers] som är angivna som klusterservrar. |
| Rapportservrar | Ger åtkomst till [!DNL Report]-datorer som ansluter till [!DNL Insight Server]. |

Medlemmar i en åtkomstkontrollgrupp definieras med hjälp av IP-adresser eller SSL-certifikatinformation.

Om ett SSL-certifikat inte är tillgängligt kan en IP-adress användas för att definiera en gruppmedlem. Den typiska installationen av [!DNL Insight] innehåller ett SSL-certifikat, medan det är valfritt att använda certifikat för [!DNL Sensor(s)]. För [!DNL Insight Server] definieras klusterservrar med IP-adresser i stället för SSL-certifikat.

Följande koder kan användas för att definiera gruppmedlemmar:

| Åtkomsttypskod | Definition |
|---|---|
| O | Organisation |
| CN | Gemensamt namn |
| L | Lokalitet |
| ST | Delstat eller provins |
| C | Land |
| OU | Organisationsenhet |
| E-post | E-postadress |
