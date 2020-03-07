---
description: 'null'
solution: Analytics
title: Värdeprofilmått
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Värdeprofilmått{#value-profile-metrics}

| Mått | Formel | Nivå | Beskrivning |
|---|---|---|---|
| Konvertering | [!DNL-[sessioner, inte Session_Value=#0]/sessioner] | Session | Procentandel sessioner som genererade affärsvärde (enligt definition i affärsvärdemodellen). |
| Värdeprocent | [!DNL Value/total(Value)] | Session | Procentandel av det totala värdet som genererades från den valda sessionsuppsättningen. |
| Värde | [!DNL sum(Session_Value, Session)*0.01] | Session | Det totala genererade affärsvärdet i dollar (enligt definition i affärsvärdesmodellen). |
| Värdehändelser | [!DNL-[sessioner, inte Session_Value=#0]] | Session | Antal sessioner som genererade affärsvärde (enligt definition i affärsvärdemodellen). |
| Värdehändelser per besökare | [!DNL (Value_Events/Visitors) by Visitor] | Besökare | Genomsnittligt antal sessioner för varje besökare som genererade ett affärsvärde (enligt definition i affärsvärdesmodellen). |
| Värde per besökare | [!DNL (Value/Visitors) by Visitor] | Besökare | Det genomsnittliga affärsvärde som genereras av varje besökare i dollar. |
