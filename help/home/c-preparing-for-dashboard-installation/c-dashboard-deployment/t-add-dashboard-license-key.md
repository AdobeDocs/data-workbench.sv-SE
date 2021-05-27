---
description: Kontrollpanelsprodukten kräver en licens från Adobe ClientCare.
title: Lägg till licensnyckel för instrumentpanel
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 0%

---

# Lägg till licensnyckel för instrumentpanel{#add-dashboard-license-key}

Kontrollpanelsprodukten kräver en licens från Adobe ClientCare.

1. Öppna **[!UICONTROL SQL Management Studio]** som administratör.
1. Öppna databasen som har skapats av kontrollpanelen (till exempel thinclientdb).
1. Högerklicka på tabellen **[!UICONTROL Configuration]** och klicka på **[!UICONTROL Edit Top 200 Rows]**.
1. Hitta fältet **[!UICONTROL licenseKey]** och ange nyckeln som tillhandahålls av Adobe ClientCare i kolumnen **[!UICONTROL Value]**.
1. Starta om **[!UICONTROL Application Pool]** i **[!UICONTROL IIS Manager Console]**.
