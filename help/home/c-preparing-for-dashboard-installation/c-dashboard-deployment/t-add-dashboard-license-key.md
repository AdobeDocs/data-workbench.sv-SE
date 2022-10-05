---
description: Kontrollpanelsprodukten kräver en licens från Adobe ClientCare.
title: Lägg till licensnyckel för instrumentpanel
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 0%

---

# Lägg till licensnyckel för instrumentpanel{#add-dashboard-license-key}

{{eol}}

Kontrollpanelsprodukten kräver en licens från Adobe ClientCare.

1. Öppna **[!UICONTROL SQL Management Studio]** som administratör.
1. Öppna databasen som har skapats av kontrollpanelen (till exempel thinclientdb).
1. Högerklicka på **[!UICONTROL Configuration]** tabell och klicka **[!UICONTROL Edit Top 200 Rows]**.
1. Hitta **[!UICONTROL licenseKey]** och ange nyckeln som tillhandahålls av Adobe ClientCare i **[!UICONTROL Value]** kolumn.
1. Starta om **[!UICONTROL Application Pool]** i **[!UICONTROL IIS Manager Console]**.
