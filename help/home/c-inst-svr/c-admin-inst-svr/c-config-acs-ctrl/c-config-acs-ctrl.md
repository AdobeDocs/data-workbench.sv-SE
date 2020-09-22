---
description: Konfigurationsfilen Access Control.cfg definierar de åtkomstkontrollgrupper som används av Insight Server för att tilldela behörigheter till filer baserat på attributen (OU, CN och så vidare) för den inkommande anslutningens certifikat.
solution: Analytics
title: Konfigurera åtkomstkontroll
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 0%

---


# Konfigurera åtkomstkontroll{#configuring-access-control}

Konfigurationsfilen Access Control.cfg definierar de åtkomstkontrollgrupper som används av Insight Server för att tilldela behörigheter till filer baserat på attributen (OU, CN och så vidare) för den inkommande anslutningens certifikat.

**Rekommenderad frekvens:** Vid behov

[!DNL Insight Server] tillhandahåller konfigurerbara åtkomstkontrollgrupper för att hantera säkerheten för anslutningar till [!DNL Insight Server]. Åtkomstkontrollgrupper identifierar användare som har behörighet att utföra administrativa funktioner via [!DNL Insight].

Om du behöver ge åtkomst till nya användare eller nya datorer, till exempel när du lägger till en dator i ett [!DNL Insight Server] kluster, redigerar du bara konfigurationsfilen för åtkomstkontroll.
