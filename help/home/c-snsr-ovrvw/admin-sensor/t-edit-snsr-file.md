---
description: Sensorkonfigurationsfilen, txlogd.conf, innehåller parametrar som Sensor använder för att upprätta en anslutning till data workbench-servern.
solution: Analytics
title: Redigera filen txlog.conf för sensorn
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---


# Redigera filen txlog.conf för sensorn{#editing-the-sensor-txlogd-conf-file}

Sensorkonfigurationsfilen, txlogd.conf, innehåller parametrar som Sensor använder för att upprätta en anslutning till data workbench-servern.

Dessa parametrar inkluderar serverns adress, portnummer och kommunikationsprotokoll (HTTP eller HTTPS). Konfigurationsfilen innehåller även alternativ för filtrering av logginnehåll och kontrollerad experimentinformation. Kontrollerade experiment gör det möjligt för webbplatsdesigners att experimentera med innehåll eller designändringar på en delmängd av alla besökare.

När du ändrar andra [!DNL txlogd.conf] parametrar, t.ex. IP-adressen för [!DNL data workbench server] eller namnet på [!DNL Sensor]filen, kan du helt enkelt ersätta [!DNL txlogd.conf] med den uppdaterade versionen och [!DNL Sensor] då hämtas ändringarna automatiskt. På vissa system kanske du inte kan redigera eller ersätta filen utan att stoppa webbservern eller överföringsprocessen.

**Öppna och redigera txlogd.conf**

1. Bläddra till [!DNL Sensor] installationskatalogen och öppna [!DNL txlogd.conf] filen i en textredigerare.
1. Redigera filen efter behov.
1. Spara och stäng filen.

   * Platsen för den kontrollerade experimentella konfigurationsfilen (definieras av parametern ExpFile i [!DNL txlogd.conf] filen) ska finnas i en katalog på webbservern som är tillgänglig för webbinnehållsutvecklarna eller styrs av ditt innehållshanteringssystem.
   * Värdet i parametern ExpCookieURL är en virtuell sida som används för att testa webbplatser. En användare som besöker den sidan får ett nytt spårnings-ID.

Mer information om hur du arbetar med [!DNL txlogd.conf]finns hos Adobe Consulting Services.
