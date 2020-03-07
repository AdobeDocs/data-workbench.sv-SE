---
description: Kontrollpanelsprodukten kräver en licens från Adobe ClientCare.
solution: Analytics
title: Lägg till licensnyckel för instrumentpanel
topic: Data workbench
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lägg till licensnyckel för instrumentpanel{#add-dashboard-license-key}

Kontrollpanelsprodukten kräver en licens från Adobe ClientCare.

1. Öppna **[!UICONTROL SQL Management Studio]** som administratör.
1. Öppna databasen som har skapats av kontrollpanelen (till exempel thinclientdb).
1. Högerklicka på **[!UICONTROL Configuration]** tabellen och klicka **[!UICONTROL Edit Top 200 Rows]**.
1. Hitta **[!UICONTROL licenseKey]** fältet och ange nyckeln från Adobe ClientCare i **[!UICONTROL Value]** kolumnen.
1. Starta om **[!UICONTROL Application Pool]** i **[!UICONTROL IIS Manager Console]**.
