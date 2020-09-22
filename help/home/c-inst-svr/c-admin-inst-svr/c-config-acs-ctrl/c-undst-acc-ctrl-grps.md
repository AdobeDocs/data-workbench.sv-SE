---
description: Det finns fem fördefinierade åtkomstkontrollsgrupper, men du kan skapa och hantera ytterligare grupper efter behov.
solution: Analytics
title: Om åtkomstkontrollgrupper
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
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
| Användare | Ger skrivskyddad åtkomst till de element som krävs för att en [!DNL Insight] användare ska kunna utföra grundläggande analysåtgärder. |
| Avancerade användare | Ger skrivskyddad åtkomst till de element som krävs för att en [!DNL Insight] användare ska kunna utföra grundläggande analysåtgärder samt läs- och skrivåtkomst till [!DNL Profiles] mappen för att ändra profiler. |
| Klusterservrar | Tillåter åtkomst till [!DNL Insight Servers] som är angivna som klusterservrar. |
| Rapportservrar | Tillåter åtkomst till [!DNL Report] datorer som ansluter till [!DNL Insight Server]. |

Medlemmar i en åtkomstkontrollgrupp definieras med hjälp av IP-adresser eller SSL-certifikatinformation.

Om ett SSL-certifikat inte är tillgängligt kan en IP-adress användas för att definiera en gruppmedlem. Den typiska installationen av [!DNL Insight] innehåller ett SSL-certifikat, medan användningen av certifikat för [!DNL Sensor(s)] är valfri. Klusterservrar [!DNL Insight Server]definieras till exempel med IP-adresser i stället för SSL-certifikat.

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

