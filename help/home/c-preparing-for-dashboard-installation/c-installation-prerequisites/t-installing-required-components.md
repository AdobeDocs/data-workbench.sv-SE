---
description: Steg för att installera de nödvändiga Microsoft-komponenterna.
title: Installerar nödvändiga komponenter
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# Installerar nödvändiga komponenter{#installing-required-components}

Steg för att installera de nödvändiga Microsoft-komponenterna.

1. Installera Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Detta måste installeras först efter installation och konfigurering av IIS-webbrollen.

1. Följ guiden och välj standardinställningar där du uppmanas att slutföra installationen.
1. Kontrollera att ASP.NET v.4.0-programpoolen har lagts till i listan **[!UICONTROL Application Pools]** i IIS när installationen är klar.
1. Installera Microsoft SQL Server-databasen.

   Använd valfri version av SQL Server 2008 eller 2008 R2 (Express stöds) med hanteringsverktyg (Adobe rekommenderar SQL Server 2008 R2 SP1 - Express Edition). 1. För en allmän installation utan att befintliga SQL Server-instanser körs i förväg väljer du alternativet **[!UICONTROL Default Instance]** på skärmen **[!UICONTROL Instance Configuration]**.
1. För resten av konfigurationsalternativen följer du guiden och väljer standardinställningar när du uppmanas att slutföra installationen.
1. Installera Microsoft Web Deploy v2.0.

   För de flesta installationer går det bra att installera **[!UICONTROL Typical]**. Om du tänker utföra fjärrdistributioner måste du dock göra en fullständig installation (välj **[!UICONTROL Complete]**).

   När alla nödvändiga komponenter har installerats på rätt sätt kan du förbereda data workbench-servrarna för att kommunicera med instrumentpanelen.
