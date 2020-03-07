---
description: Steg för att installera de nödvändiga Microsoft-komponenterna.
solution: Analytics
title: Installerar nödvändiga komponenter
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installerar nödvändiga komponenter{#installing-required-components}

Steg för att installera de nödvändiga Microsoft-komponenterna.

1. Installera Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Detta måste installeras först efter installation och konfigurering av IIS-webbrollen.

1. Följ guiden och välj standardinställningar där du uppmanas att slutföra installationen.
1. Kontrollera att ASP.NET v.4.0-programpoolen har lagts till i listan i IIS när installationen är **[!UICONTROL Application Pools]** klar.
1. Installera Microsoft SQL Server-databasen.

   Använd valfri version av SQL Server 2008 eller 2008 R2 (Express stöds) med hanteringsverktyg (Adobe rekommenderar SQL Server 2008 R2 SP1 - Express Edition). 1. Om du vill installera en allmän installation utan att köra befintliga SQL Server-instanser i förväg väljer du alternativet **[!UICONTROL Default Instance]** på **[!UICONTROL Instance Configuration]** skärmen.
1. För resten av konfigurationsalternativen följer du guiden och väljer standardinställningar när du uppmanas att slutföra installationen.
1. Installera Microsoft Web Deploy v2.0.

   För de flesta installationer fungerar installationen som den ska **[!UICONTROL Typical]** . Om du tänker utföra fjärrdistributioner måste du dock göra en fullständig installation (välj **[!UICONTROL Complete]**).

   När alla nödvändiga komponenter har installerats på rätt sätt kan du förbereda data workbench-servrarna för att kommunicera med instrumentpanelen.
