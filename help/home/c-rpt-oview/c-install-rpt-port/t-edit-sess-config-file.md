---
description: I rapportportalen används informationen i en konfigurationsfil som kallas global.asa för att initiera användarsessioner.
title: Redigera sessionskonfigurationsfilen
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Redigera sessionskonfigurationsfilen{#edit-the-session-configuration-file}

{{eol}}

I rapportportalen används informationen i en konfigurationsfil som kallas global.asa för att initiera användarsessioner.

När du installerar [!DNL Report Portal]måste du redigera den här filen. The [!DNL global.asa] filen finns i mappen \*PortalName*\PortalASP\.

>[!NOTE]
>
>Ändra inga andra parametrar i den här konfigurationsfilen.

1. Öppna [!DNL global.asa] i en textredigerare som Anteckningar.
1. Valfritt. Ge användarna åtkomst [!DNL Report Portal] utan autentisering ändrar du värdet för parametern Session(&quot;In&quot;) till true. Standardvärdet är false, vilket autentiserar alla användare som försöker få åtkomst [!DNL Report Portal].
1. Om [!DNL Report Portal] är installerat på en annan enhet än C-enheten ändrar du värdet på parametern Session(&quot;Drive&quot;) till rätt enhetsplats.
1. För parametern Session(&quot;DBPath&quot;) ändrar du värdet så att det motsvarar sökvägen till databasen som innehåller den information som krävs för att autentisera [!DNL Report Portal] -användare. Inkludera inte enhetsbokstaven, men se till att inkludera ett avslutande snedstreck.

   Exempel: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Spara filen.
1. Verifiera att [!DNL Report Portal] filer har installerats på rätt sätt och kan nås via den virtuella katalog de har. Öppna följande sida i webbläsaren:

   https://*DinServeradress*/*DittPortalNamn*

   Exempel: [!DNL https://localhost/VisualReportPortal]

   Om [!DNL Report Portal] ASP:er har installerats korrekt och du bör se portalinloggningssidan. Om du inte ser den här sidan kontrollerar du att ASP är aktiverat på din IIS och dubbelkontrollerar dina virtuella katalogmappningar.
