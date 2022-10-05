---
description: Det här avsnittet är en snabbguide som innehåller de steg som minst krävs för att ställa in och schemalägga skript för att veckovis bearbeta loggfilerna. Detta kan användas som referenshandbok för att konfigurera eller ändra dina profiler.
title: Skript för veckovis ombearbetning
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Skript för veckovis ombearbetning{#scripting-to-weekly-reprocess}

{{eol}}

Det här avsnittet är en snabbguide som innehåller de steg som minst krävs för att ställa in och schemalägga skript för att veckovis bearbeta loggfilerna. Detta kan användas som referenshandbok för att konfigurera eller ändra dina profiler.

## Vad är Reprocess? {#section-7e335aacc199488592e78a835e2649fe}

Läsa in data till DWB baserat på ändringar i datakällor, offlinedatakällor eller tidsperiod. Skriptet bearbetar startdatumparametern igen i *Loggbearbetning.cfg* -fil.

## Förutsättningar {#section-804acce5df4942469c9313535627038a}

Report Suite-ID, antal månadsdata ska vara tillgängliga i DWB. Mappen Perl64 bör vara tillgänglig i mappen C:\ drive.

## Bearbeta loggar igen {#section-565d3e1f0df14127a97d9beecd14f02f}

Tillhandahåll ovanstående information (krav) i Windows-kommandoskript *Reprocess.bat* finns i mappen *\scripts\Log Processing* på huvudservern för FSU.

Skriptet anropar två klientspecifika skript internt: En för att bearbeta om data och en annan för e-postavisering. Dessa två skript finns också i *\scripts\Log Processing* mapp.

Skriptet ändrar ombearbetningsparametrar i *Loggbearbetning.cfg* -fil.

## Rullande fönster för loggar {#section-ed5f44d890b34523ab33da7aa0ae3990}

Ange information (krav) i Windows-kommandoskript *loggprocesingdate.bat* finns i mappen *\scripts\Scripository* på den ledande FSU-servern. Skriptet anropar två klientspecifika skript internt: Ett för att ställa in startdatum för loggar och ett för e-postaviseringar. Dessa två skript är också tillgängliga i* \scripts\Scripository*

Ange rapportsvitens ID och antal månader i filen* logprocessing.bat*.

Skriptet ändrar startdatumparametern i *Loggbearbetning.cfg*.

>[!NOTE]
>
>Om *Scripository* mappen är inte tillgänglig, följ processen nedan för att kopiera *Scripository* och gör ändringar i ovanstående filer med hjälp av kundspecifik information. Och ange din e-postadress för att få en varning om något fel inträffar.

## Schemaläggningsskript {#section-063cf0c755dc47d28d60947d8d43d0e9}

Följ de här stegen för att schemalägga skripten i aktivitetsschemaläggaren i Windows.

1. Schemalägg skriptet i Windows uppgiftsschemaläggare.

   * Öppna Schemaläggaren: Högerklicka på **Schemaläggarens bibliotek** och klicka **Skapa uppgift**.

   * I **Allmänt** -fliken anger ett aktivitetsnamn och väljer **Alternativ**.

   * Under **Utlösare** flik, klicka **Nytt** och ett nytt fönster öppnas.

   * Under **Åtgärder** flik, klicka **Nytt** och ett nytt fönster öppnas. Ange sedan skriptinformation och andra alternativ. (Börja i har en sökväg där skript placeras).

1. Validering: Högerklicka och kör jobbet och verifiera ändringarna i *Loggbehandling.cfg* -fil. Ett e-postmeddelande skickas till det e-post-ID som anges i skriptet.
