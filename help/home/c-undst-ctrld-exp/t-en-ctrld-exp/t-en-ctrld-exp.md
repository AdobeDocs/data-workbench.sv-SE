---
description: Om du vill aktivera kontrollerade försök måste någon med administratörsåtkomst till dina webb- eller programservrar ändra parametern ExpFile i Sensor-konfigurationsfilen (kallas vanligtvis txlogd.conf) på varje webb- eller programserver i webbklustret där en Sensor är installerad.
solution: Analytics,Analytics
title: Aktivera kontrollerad experimentering
uuid: 27d68fad-ae2d-4a2e-b449-fbaf88286cfa
exl-id: 53c18524-6050-4708-af63-9e8ef8da389e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Aktivera kontrollerad experimentering{#enabling-controlled-experimentation}

Om du vill aktivera kontrollerade försök måste någon med administratörsåtkomst till dina webb- eller programservrar ändra parametern ExpFile i Sensor-konfigurationsfilen (kallas vanligtvis txlogd.conf) på varje webb- eller programserver i webbklustret där en Sensor är installerad.

Dessutom kan två andra parametrar i den här filen ändras för att implementera ett testverktyg (parametern ExpCookieURL) eller för att mappa om stora avsnitt på webbplatsen (parametern ExpPartialMatch). I det här kapitlet finns mer information om de här parametrarna.

**Så här redigerar du filen txlogd.conf**

Om du har administratörsåtkomst utför du följande steg. Om du inte har administratörsbehörighet kontaktar du systemarkitekten för att begära ändringarna och ger dem följande steg.

1. Navigera till installationsmappen [!DNL Sensor] på en webb- eller programserver i webbklustret där [!DNL Sensor] är installerat.
1. Öppna konfigurationsfilen [!DNL Sensor] (vanligtvis namngiven med [!DNL txlogd.conf]) med en textredigerare och redigera filen enligt [Ändra ExpFile-parametern](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   (Alternativt i [Ändra parametern ExpCookieURL (valfritt)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf) och [Ändra parametern ExpPartialMatch (valfritt)](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e).)

1. Spara och stäng filen.
1. Upprepa den här proceduren för varje webb- eller programserver i webbklustret där en [!DNL Sensor] är installerad.
