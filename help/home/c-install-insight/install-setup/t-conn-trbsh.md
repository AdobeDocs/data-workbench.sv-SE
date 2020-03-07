---
description: Om Insight inte kan ansluta till Insight Server(s) med de angivna inställningarna visas en röd nod i Serverhanteraren.
title: Felsökning av anslutning
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Felsökning av anslutning{#connection-troubleshooting}

Om Insight inte kan ansluta till Insight Server(s) med de angivna inställningarna visas en röd nod i Serverhanteraren.

Detta kan till exempel inträffa om du konfigurerar anslutningen felaktigt eller om du inte har behörighet att visa [!DNL Insight Server’s] statusen.

**För att avgöra varför Insight inte kan upprätta en anslutning**

1. Högerklicka på den röda servernoden och klicka på **[!UICONTROL Detailed Status]**.
1. Klicka [!DNL Detailed Status] och expandera de numrerade objekten i **[!UICONTROL Network Connections]** gränssnittet. Parametern [!DNL Status] ger information om varför Insight inte kan upprätta en anslutning:

   * En statuskod i 500-talet anger att det finns ett konfigurationsfel.
   * En statuskod på 403 anger vanligtvis att du inte har behörighet att visa serverns status.

Du kan visa ytterligare statusinformation i [!DNL insight.log] filen. Loggfilen finns i mappen [!DNL Trace] där du installerade Insight. Om du vill visa filen öppnar du den i en textredigerare, t.ex. Anteckningar.

Om du behöver hjälp med att förstå informationen i [!DNL insight.log] filen kontaktar du först systemadministratören. Om du behöver mer hjälp kan du kontakta Adobes kundtjänst.
