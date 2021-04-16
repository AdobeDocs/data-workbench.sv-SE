---
description: Värdeprofilmått
title: Värdeprofilmått
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 1%

---

# Värdeprofilmått{#value-profile-metrics}

| Mått | Formel | Nivå | Beskrivning |
|---|---|---|---|
| Konvertering | `Sessions[not Session_Value=#0]/Sessions` | Session | Procentandel sessioner som genererade affärsvärde (enligt definition i affärsvärdemodellen). |
| Värdeprocent | `Value/total(Value)` | Session | Procentandel av det totala värdet som genererades från den valda sessionsuppsättningen. |
| Värde | `sum(Session_Value, Session)*0.01` | Session | Det totala genererade affärsvärdet i dollar (enligt definition i affärsvärdesmodellen). |
| Värdehändelser | `Sessions[not Session_Value=#0]` | Session | Antal sessioner som genererade affärsvärde (enligt definition i affärsvärdemodellen). |
| Värdehändelser per besökare | `(Value_Events/Visitors) by Visitor` | Besökare | Genomsnittligt antal sessioner för varje besökare som genererade ett affärsvärde (enligt definition i affärsvärdesmodellen). |
| Värde per besökare | `(Value/Visitors) by Visitor` | Besökare | Det genomsnittliga affärsvärde som genereras av varje besökare i dollar. |
