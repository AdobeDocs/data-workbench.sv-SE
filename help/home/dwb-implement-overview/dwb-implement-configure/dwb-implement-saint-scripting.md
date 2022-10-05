---
description: I det här avsnittet förklaras det sanna skrubberskriptet.
title: Skript för SAINT Scrubber
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
exl-id: 5f6d92b1-baaa-4d67-a1c2-ce7d51affb17
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---

# Skript för SAINT Scrubber{#scripting-for-the-saint-scrubber}

{{eol}}

I det här avsnittet förklaras det sanna skrubberskriptet.

## Översikt över klassificering av SAINT {#section-b840a99f10684bb4b58e844a515d0d79}

Klassificeringen kallas även akronymen SAINT för SiteCatalyst Attribute Importing and Naming Tool.

När vi&quot;klassificerar&quot; en variabel i SiteCatalyst upprättar du en relation mellan en variabel och metadata som är relaterade till den variabeln. Klassificeringar används oftast i Campaigns-området, så jag kommer att använda dem som ett sätt att förklara dem. De flesta kunder skickar kampanjtrafik till sin webbplats med hjälp av en spårningskod. Den här spårningskoden är en identifierare som kan representera ett specifikt nyckelord som köpts på Google, till exempel&quot;goog123&quot;. Den här identifieraren skickas till s.campaign-variabeln så att du kan se vilka webbplatsens framgångshändelser som inträffar efter att besökare kommer till er webbplats från den kampanjkoden.

Men tänk om ni, i stället för att bara visa kampanjer med hjälp av spårningskoden, vill se kampanjresultaten med sökmotorn, nyckelordet eller kampanjkanalen? Måste du skapa en ny konverteringsvariabel för sökmotorn, en annan för nyckelord och en annan för Campaign Channel? I så fall använder ni upp många av era femtio variabler bara på Campaigns! Tack och lov kan du använda klassificeringar för att göra livet enklare! Eftersom varje spårningskod kan ha en sökmotor, ett nyckelord eller en kampanjkanal kan du helt enkelt skapa tre klassificeringar av kampanjvariabeln som representerar varje. Du berättar i stort sett för SiteCatalyst att det finns ett direkt samband mellan Campaigns-variabeln och de tre andra&quot;metadata-värdena&quot;. På så sätt kan du med SiteCatalyst segmentera och tona ned webbplatsens Success Events med alla fyra variablerna utan ytterligare taggning.

## SAINT-navigeringsskript i DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Det här skriptet används när du hämtar data från klassificering av SAINT till DWB. Skriptet *SaintScrubber.dat* placeras normalt under *\Scripts\Scripository* på FSU:n.

Huvudsyftet med det här skriptet är att ta bort rubriken i `<discoiqbr>` SAINT Klassificeringsfiler. Dessutom räknas talet om kolumnen som anges i kolumnrubrikraden och kontrollerar alla datarader. Om det finns rader med färre eller fler kolumner tas dessa rader bort från filen.

The *SaintScrubber.dat* anropar *saint_scrubber.pl *skriptet internt. Nedan finns information om den här skriptfilen:

Sökväg: *E:\Scripts\Scripository\Library\Perl*

Skriptargument:

1. Indatamapp (obligatoriskt): source_directory
1. Utdatamapp (obligatoriskt): mål_katalog
1. Avgränsare (obligatoriskt): delimiter
1. Avvisa mapp (valfritt) (Parametern kan lämnas tom eller utelämnas från kommandoraden)
1. Loggmapp (valfritt)(Parametern kan lämnas tom eller utelämnas från kommandoraden)

Steg som utförs i Perl-skriptet:

1. Ersätt blankettmatningar, radmatningar, radmatningar, tabbar med blanksteg.
1. Ta bort de dubbla byte som tolkas som ett kontrolltecken i UTF-8 BMP (Basic Multilingual Plane) förutom:

   * 9 vågrät flik
   * 10 rader
   * 12 formulärfeed
   * 13 vagnretur
   * Använd nyckelordet pipe som avgränsare för | t.ex.: avgränsarrör
   * Ta bort andra felande tecken
   * Efter rensningen ovan tas alla rader med ett antal kolumner bort från den första dataraden (inte tomma eller kommentarer)
   * Stöd för valfria avvisningsfiler för avvisade rader i stället för att bara hoppa över dem
   * Stöd för rekursiv indatamapp; generera utdatamappar med samma struktur
   * Flytta bearbetade indatafiler till bearbetade undermappar så att skriptet inte upprepar arbetet när det körs igen på samma befintliga indatamapp
   * Identifiera datum i filnamn i workbench. sortera först efter datum och sedan alfa, oavsett mappnamn. Detta säkerställer att sekvensen är korrekt oavsett vilken typ av workbench-fil (ecom, non-ecom) eller rapportsvit-ID som används (om du bearbetar flera rapportsviter till en enda Insight-datauppsättning).
   * Stöd för e-postaviseringar `<discoiqbr>`
