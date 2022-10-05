---
description: Sensorkonfigurationsfilen, txlogd.conf, innehåller parametrar som Sensor använder för att upprätta en anslutning till data workbench-servern.
title: Redigera filen txlog.conf för sensorn
uuid: e7f41c14-9047-4e1a-be0f-8acc8ecb1160
exl-id: ed243bb4-cf87-4bcf-89d6-5ff5cec3bc6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# Redigera filen txlog.conf för sensorn{#editing-the-sensor-txlogd-conf-file}

{{eol}}

Sensorkonfigurationsfilen, txlogd.conf, innehåller parametrar som Sensor använder för att upprätta en anslutning till data workbench-servern.

Dessa parametrar inkluderar serverns adress, portnummer och kommunikationsprotokoll (HTTP eller HTTPS). Konfigurationsfilen innehåller även alternativ för filtrering av logginnehåll och kontrollerad experimentinformation. Kontrollerade experiment gör det möjligt för webbplatsdesigners att experimentera med innehåll eller designändringar på en delmängd av alla besökare.

Vid ändring av andra [!DNL txlogd.conf] parametrar, till exempel IP-adressen för [!DNL data workbench server] eller namnet på [!DNL Sensor]kan du helt enkelt ersätta [!DNL txlogd.conf] med den uppdaterade versionen och [!DNL Sensor] kommer att hämta upp ändringarna automatiskt. På vissa system kanske du inte kan redigera eller ersätta filen utan att stoppa webbservern eller överföringsprocessen.

**Öppna och redigera txlogd.conf**

1. Bläddra till [!DNL Sensor] installationskatalogen och öppna [!DNL txlogd.conf] i en textredigerare.
1. Redigera filen efter behov.
1. Spara och stäng filen.

   * Platsen för konfigurationsfilen för det kontrollerade försöket (definieras av parametern ExpFile i [!DNL txlogd.conf] -filen) ska finnas i en katalog på webbservern som är tillgänglig för webbinnehållsutvecklare eller som styrs av ditt innehållshanteringssystem.
   * Värdet i parametern ExpCookieURL är en virtuell sida som används för att testa webbplatser. En användare som besöker den sidan får ett nytt spårnings-ID.

Mer information om hur du arbetar med [!DNL txlogd.conf], kontakta Adobe Consulting Services.
