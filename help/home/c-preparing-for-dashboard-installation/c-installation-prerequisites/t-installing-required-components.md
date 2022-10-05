---
description: Steg för att installera de nödvändiga Microsoft-komponenterna.
title: Installerar nödvändiga komponenter
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# Installerar nödvändiga komponenter{#installing-required-components}

{{eol}}

Steg för att installera de nödvändiga Microsoft-komponenterna.

1. Installera Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Detta måste installeras först efter installation och konfigurering av IIS-webbrollen.

1. Följ guiden och välj standardinställningar där du uppmanas att slutföra installationen.
1. Kontrollera att ASP.NET v.4.0-programpoolen har lagts till i **[!UICONTROL Application Pools]** i IIS.
1. Installera Microsoft SQL Server-databasen.

   Använd valfri version av SQL Server 2008 eller 2008 R2 (Express stöds) med hanteringsverktyg (Adobe rekommenderar SQL Server 2008 R2 SP1 - Express Edition). 1. För en allmän installation utan att befintliga SQL Server-instanser körs i förväg, välj **[!UICONTROL Default Instance]** på **[!UICONTROL Instance Configuration]** skärm.
1. För resten av konfigurationsalternativen följer du guiden och väljer standardinställningar när du uppmanas att slutföra installationen.
1. Installera Microsoft Web Deploy v2.0.

   För de flesta installationer är **[!UICONTROL Typical]** installationen är bra. Om du tänker göra fjärrdistributioner måste du dock göra en fullständig installation (välj **[!UICONTROL Complete]**).

   När alla nödvändiga komponenter har installerats på rätt sätt kan du förbereda data workbench-servrarna för att kommunicera med instrumentpanelen.
