---
description: När Sensor samlar in händelsedata från en webbserver, ställer Sensor automatiskt in en beständig cookie för varje besökare som innehåller en liten slumpmässig identifierare, utan att registrera någon personligt identifierande information.
solution: Insight
title: Hur identifierar sensorn besökare och sessioner?
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hur identifierar sensorn besökare och sessioner?{#how-does-sensor-identify-visitors-and-sessions}

När Sensor samlar in händelsedata från en webbserver, ställer Sensor automatiskt in en beständig cookie för varje besökare som innehåller en liten slumpmässig identifierare, utan att registrera någon personligt identifierande information.

Denna Adobe-cookie används för att identifiera den unika besökaren och alla dess tillhörande sessioner.

Som standard hämtar [!DNL Sensor] alla W3C Extended Log File-fält från varje HTTP-huvud, men du kan konfigurera så [!DNL Sensor] att alla rubriker som överförs mellan klienten och servern samlas in. Mer information om händelsedatafält som samlats in av [!DNL Sensor] i [!DNL .vsl] filer finns i [Händelsedatafält](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Vissa besökares webbläsare lagrar inte cookies permanent, och ett mycket litet antal besökares webbläsare accepterar inte cookies alls (till och med sessionscookies). Även om de bara står för en bråkdel av en webbplats totala trafik kan de leda till en betydande felräkning om varje sidvy av en sådan besökare felaktigt räknas som en hel session, vilket görs av en del program för loggfilsanalys. Adobe löser detta problem genom att göra det möjligt för er att analysera besökare med och utan att använda cookies.

Mer information om filtret Brutna sessioner finns i *Data Workbench Sensor Guide*.
