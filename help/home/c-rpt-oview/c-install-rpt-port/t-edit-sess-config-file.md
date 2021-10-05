---
description: I rapportportalen används informationen i en konfigurationsfil som kallas global.asa för att initiera användarsessioner.
title: Redigera sessionskonfigurationsfilen
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Redigera sessionskonfigurationsfilen{#edit-the-session-configuration-file}

I rapportportalen används informationen i en konfigurationsfil som kallas global.asa för att initiera användarsessioner.

När du installerar [!DNL Report Portal] måste du redigera den här filen enligt vad som anges. Filen [!DNL global.asa] finns i mappen \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Ändra inga andra parametrar i den här konfigurationsfilen.

1. Öppna [!DNL global.asa]-filen i en textredigerare, t.ex. Anteckningar, på den dator där IIS körs.
1. Valfritt. Om du vill att användare ska kunna komma åt [!DNL Report Portal] utan autentisering ändrar du värdet för parametern Session(&quot;In&quot;) till true. Standardvärdet är false, vilket autentiserar alla användare som försöker få åtkomst till [!DNL Report Portal].
1. Om din [!DNL Report Portal] är installerad på en annan enhet än C-enheten ändrar du värdet på parametern Session(&quot;Drive&quot;) till rätt enhetsplats.
1. För parametern Session(&quot;DBPath&quot;) ändrar du värdet så att det motsvarar sökvägen till databasen som innehåller den information som behövs för att autentisera [!DNL Report Portal]-användare. Inkludera inte enhetsbokstaven, men se till att inkludera ett avslutande snedstreck.

   Exempel: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Spara filen.
1. Kontrollera att [!DNL Report Portal]-filerna har installerats korrekt och kan nås via den virtuella katalogen genom att öppna följande sida i webbläsaren:

   https://*DinServeradress*/*DittPortalNamn*

   Exempel: [!DNL https://localhost/VisualReportPortal]

   Om ASP:erna [!DNL Report Portal] har installerats korrekt bör du se portalinloggningssidan. Om du inte ser den här sidan kontrollerar du att ASP är aktiverat på din IIS och dubbelkontrollerar dina virtuella katalogmappningar.
