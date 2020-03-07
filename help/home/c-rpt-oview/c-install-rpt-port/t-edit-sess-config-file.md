---
description: I rapportportalen används informationen i en konfigurationsfil som kallas global.asa för att initiera användarsessioner.
solution: Analytics
title: Redigera sessionskonfigurationsfilen
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Redigera sessionskonfigurationsfilen{#edit-the-session-configuration-file}

I rapportportalen används informationen i en konfigurationsfil som kallas global.asa för att initiera användarsessioner.

När du installerar [!DNL Report Portal]måste du redigera filen enligt anvisningarna. Filen finns [!DNL global.asa] i mappen \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Ändra inga andra parametrar i den här konfigurationsfilen.

1. Öppna filen i en textredigerare, t.ex. Anteckningar, på den dator där IIS körs. [!DNL global.asa]
1. Valfritt. Om du vill att användare ska kunna få åtkomst [!DNL Report Portal] utan autentisering ändrar du värdet för parametern Session(&quot;In&quot;) till true. Standardvärdet är false, vilket autentiserar alla användare som försöker få åtkomst [!DNL Report Portal].
1. Om du [!DNL Report Portal] har installerat på en annan enhet än C-enheten ändrar du värdet på parametern Session(&quot;Drive&quot;) till rätt enhetsplats.
1. För parametern Session(&quot;DBPath&quot;) ändrar du värdet så att det motsvarar sökvägen till databasen som innehåller den information som behövs för att autentisera [!DNL Report Portal] användare. Inkludera inte enhetsbokstaven, men se till att inkludera ett avslutande snedstreck.

   Exempel: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Spara filen.
1. Kontrollera att [!DNL Report Portal] filerna har installerats korrekt och att de kan nås via den virtuella katalogen genom att öppna följande sida i webbläsaren:

   http://*YourServerAddress*/*YourPortalName*

   Exempel: [!DNL http://localhost/VisualReportPortal]

   Om [!DNL Report Portal] ASP:erna har installerats korrekt kan du se portalinloggningssidan. Om du inte ser den här sidan kontrollerar du att ASP är aktiverat på din IIS och dubbelkontrollerar dina virtuella katalogmappningar.

