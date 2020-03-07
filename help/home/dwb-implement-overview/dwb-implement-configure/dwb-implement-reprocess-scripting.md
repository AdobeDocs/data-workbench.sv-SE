---
description: Det här avsnittet är en snabbguide som innehåller de steg som minst krävs för att ställa in och schemalägga skript för att veckovis bearbeta loggfilerna. Detta kan användas som referenshandbok för att konfigurera eller ändra dina profiler.
title: Skript för veckovis ombearbetning
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skript för veckovis ombearbetning{#scripting-to-weekly-reprocess}

Det här avsnittet är en snabbguide som innehåller de steg som minst krävs för att ställa in och schemalägga skript för att veckovis bearbeta loggfilerna. Detta kan användas som referenshandbok för att konfigurera eller ändra dina profiler.

## Vad är Reprocess? {#section-7e335aacc199488592e78a835e2649fe}

Läsa in data till DWB baserat på ändringar i datakällor, offlinedatakällor eller tidsperiod. Skriptet bearbetar parametern för startdatum i filen *Log Processing.cfg* igen.

## Förutsättningar {#section-804acce5df4942469c9313535627038a}

Report Suite-ID, antal månadsdata ska vara tillgängliga i DWB. Mappen Perl64 bör vara tillgänglig i mappen C:\ drive.

## Bearbeta loggar igen {#section-565d3e1f0df14127a97d9beecd14f02f}

Ange ovanstående information (krav) i Windows-kommandoskriptet *Reprocess.bat* som finns i mappen *\scripts\Log Processing* på Main FSU-servern.

Skriptet anropar två klientspecifika skript internt: En för att bearbeta om data och en annan för e-postavisering. Dessa två skript finns också i mappen *\scripts\Log Processing* .

Skriptet ändrar ombearbetningsparametrar i filen *Log Processing.cfg* .

## Rullande fönster för loggar {#section-ed5f44d890b34523ab33da7aa0ae3990}

Ange information (krav) i Windows-kommandoskriptet *logprocessing.bat* som finns i mappen *\scripts\Scripository* på den anslutna FSU-servern. Skriptet anropar två klientspecifika skript internt: Ett för att ställa in startdatum för loggar och ett för e-postaviseringar. Dessa två skript finns också i* \scripts\Scripository*

Ange rapportsvitens ID och antal månader i filen* logprocessing.bat*.

Skriptet ändrar parametern för startdatum i *Log Processing.cfg*.

>[!NOTE]
>
>Om *mappen Scripository* inte är tillgänglig följer du processen nedan för att kopiera mappen *Scripository* och göra ändringar i ovanstående filer med kundspecifik information. Och ange din e-postadress för att få en varning om något fel inträffar.

## Schemaläggningsskript {#section-063cf0c755dc47d28d60947d8d43d0e9}

Följ de här stegen för att schemalägga skripten i aktivitetsschemaläggaren i Windows.

1. Schemalägg skriptet i Windows uppgiftsschemaläggare.

   * Öppna Schemaläggaren: Högerklicka på **Schemaläggarens bibliotek** och klicka på **Skapa aktivitet**.

   * Ange ett aktivitetsnamn på fliken **Allmänt** och välj **Alternativ**.

   * Klicka på **Nytt** på fliken **Utlösare** så öppnas ett nytt fönster.

   * Klicka på **Nytt** på fliken **Åtgärder** så öppnas ett nytt fönster. Ange sedan skriptinformation och andra alternativ. (Börja i har en sökväg där skript placeras).

1. Validering: Högerklicka och kör jobbet och verifiera ändringarna i *loggfilen processing.cfg* . Ett e-postmeddelande skickas till det e-post-ID som anges i skriptet.

