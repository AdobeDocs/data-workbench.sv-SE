---
description: Om Insight inte kan ansluta till Insight Server(s) med de angivna inställningarna visas en röd nod i Serverhanteraren.
title: Felsökning av anslutning
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---

# Felsökning av anslutning{#connection-troubleshooting}

{{eol}}

Om Insight inte kan ansluta till Insight Server(s) med de angivna inställningarna visas en röd nod i Serverhanteraren.

Detta kan till exempel inträffa om du konfigurerar anslutningen felaktigt eller om du inte har behörighet att visa [!DNL Insight Server’s] status.

**För att avgöra varför Insight inte kan upprätta en anslutning**

1. Högerklicka på den röda servernoden och klicka på **[!UICONTROL Detailed Status]**.
1. I [!DNL Detailed Status] gränssnitt, klicka **[!UICONTROL Network Connections]** och expandera de numrerade objekten. The [!DNL Status] parameter ger information om varför Insight inte kan upprätta en anslutning:

   * En statuskod i 500-talet anger att det finns ett konfigurationsfel.
   * En statuskod på 403 anger vanligtvis att du inte har behörighet att visa serverns status.

Du kan visa ytterligare statusinformation i dialogrutan [!DNL insight.log] -fil. Loggfilen finns i [!DNL Trace] i den katalog där du installerade Insight. Om du vill visa filen öppnar du den i en textredigerare, t.ex. Anteckningar.

Om du behöver hjälp med att förstå informationen i [!DNL insight.log] först kontaktar du systemadministratören. Kontakta Adobe kundtjänst om du behöver mer hjälp.
