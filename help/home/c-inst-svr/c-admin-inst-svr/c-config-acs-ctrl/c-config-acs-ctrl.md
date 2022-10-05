---
description: Konfigurationsfilen Access Control.cfg definierar de åtkomstkontrollgrupper som används av Insight Server för att tilldela behörigheter till filer baserat på attributen (OU, CN och så vidare) för den inkommande anslutningens certifikat.
title: Konfigurera åtkomstkontroll
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 0%

---

# Konfigurera åtkomstkontroll{#configuring-access-control}

{{eol}}

Konfigurationsfilen Access Control.cfg definierar de åtkomstkontrollgrupper som används av Insight Server för att tilldela behörigheter till filer baserat på attributen (OU, CN och så vidare) för den inkommande anslutningens certifikat.

**Rekommenderad frekvens:** Vid behov

[!DNL Insight Server] ger konfigurerbara åtkomstkontrollgrupper för att hantera säkerheten för anslutningar till [!DNL Insight Server]. Åtkomstkontrollgrupper identifierar användare som får utföra administrativa funktioner via [!DNL Insight].

Om du behöver ge åtkomst till nya användare eller nya datorer, till exempel när du lägger till en dator till en [!DNL Insight Server] -kluster redigerar du bara åtkomstkontrollens konfigurationsfil.
