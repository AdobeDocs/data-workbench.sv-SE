---
description: Konfigurationsfilen Access Control.cfg definierar de åtkomstkontrollgrupper som används av Insight Server för att tilldela behörigheter till filer baserat på attributen (OU, CN och så vidare) för den inkommande anslutningens certifikat.
solution: Insight
title: Konfigurera åtkomstkontroll
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera åtkomstkontroll{#configuring-access-control}

Konfigurationsfilen Access Control.cfg definierar de åtkomstkontrollgrupper som används av Insight Server för att tilldela behörigheter till filer baserat på attributen (OU, CN och så vidare) för den inkommande anslutningens certifikat.

**Rekommenderad frekvens:** Vid behov

[!DNL Insight Server] tillhandahåller konfigurerbara åtkomstkontrollgrupper för att hantera säkerheten för anslutningar till [!DNL Insight Server]. Åtkomstkontrollgrupper identifierar användare som har behörighet att utföra administrativa funktioner via [!DNL Insight].

Om du behöver ge åtkomst till nya användare eller nya datorer, till exempel när du lägger till en dator i ett [!DNL Insight Server] kluster, redigerar du bara konfigurationsfilen för åtkomstkontroll.
