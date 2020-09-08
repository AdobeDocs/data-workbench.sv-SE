---
description: 'null'
solution: Analytics
title: Värdeprofilmått
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 2%

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
