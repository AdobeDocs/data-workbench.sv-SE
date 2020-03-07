---
description: Nya funktioner och korrigeringar i Data Workbench 6.73.
title: Versionsinformation för Data Workbench 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Versionsinformation för Data Workbench 6.73{#data-workbench-release-notes}

Nya funktioner och korrigeringar i Data Workbench 6.73.

## Versionsinformation för Data Workbench 6.73 {#topic-7655534554ac4a4b816af1bd73b06aad56757}

Nya funktioner och korrigeringar i Data Workbench 6.73.

## Korrigeringar {#section-160baf6ea04c45a993777ee4260691ed}

* Korrigerade ett problem i Workstation där användare inte kunde logga in på maskinvara med hög upplösning och hög DPI.
* Ett problem har korrigerats på servern där e-post saknades i arkivfilnamn vid IMS-inloggning.
* OpenSSL har uppdaterats till version 1.1.0h, som innehåller flera sårbarhetskorrigeringar och nya SSL-ciphers.
* Nedan listade bibliotek med öppen källkod uppdaterades till de senaste stabila versionerna

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Felloggning har lagts till när antalet rader i uppslagsfilen överstiger 357913908 rader.

## Känt fel {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench Workstation version 6.73 ansluter inte till Data Workbench-servrar version 6.61 och äldre. Orsaken är att äldre serverversioner använder en svag form av ciphers som inte stöds i version 6.73. Aktivera stöd för äldre versioner

   1. Åsidosätt SSL-chifferlistan på servern med en stark chifferlista som stöds av OpenSSL version 1.0.1h. Om du vill åsidosätta lägger du till nyckeln&quot;SSL-chiphers&quot; i filerna&quot;Communications.cfg&quot; som finns i katalogerna&quot;Components&quot; och&quot;Components for Processing Servers&quot;. Exempel: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Kontrollera att nyckeln är placerad på samma nivå som SSL-porten. Mer information finns i Inställningar för [kommunikationskonfiguration](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Placera den senaste filen trust_ca_cert.pem på server 6.61 och äldre servrar. Den här inställningen gäller för alla Workstation 6.7x-versioner.

Se [arkiverad veringsinformation](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) för Data Workbench 5.3 till 5.52.
