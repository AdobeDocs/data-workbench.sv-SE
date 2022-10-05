---
description: I profilen Geografi lagras en samling bildlager och filer.
title: Visa lager
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Visa lager{#display-layers}

{{eol}}

I profilen Geografi lagras en samling bildlager och filer.

När du visar en glob kan du välja vilket av de tillgängliga lagren som ska visas för en viss analysuppgift:

* **Blå marmor 2 km:** Det här lagret visar hela världen. När det här lagret inte är markerat visas inte glob.
* **IP-koordinater:** Det här elementpunktslagret visar latitud och longitud för platserna i din datamängd baserat på besökarens IP-adresser.
* **Postnummer:** I det här lagret visas latitud- och longitudvärdena för platser i datauppsättningen baserat på en lista över USA:s ZIP-koder som tillhandahålls av Adobe. The [!DNL Zip Points.txt] uppslagsfilen innehåller de postnummer, latitud- och longituddata som ska visas, medan [!DNL Zip Points.layer] filen innehåller de konfigurationsparametrar som behövs för att visa dessa data på jorden. Båda dessa filer lagras i mappen Profiler\Geography\Maps i Datans Workbench serverinstallationskatalog.

* ***Andra tillgängliga lagernamn:*** Varje lagernamn representerar en [!DNL .layer] filen lagras i mappen Profiler\Geography\Maps, Profiles\IP Geo-location\Maps eller mappen Profiles\IP Geo-intelligence\Maps i installationskatalogen för Insight Server.

>[!NOTE]
>
>Om du vill ha IP Geo-location- eller IP Geo-Intelligence-profilen måste du prenumerera på antingen IP Geo-location- eller IP Geo-Intelligence-datatjänsten.

Om du vill styra i vilken ordning lagren ska visas kan du använda en [!DNL order.txt] -fil. Se [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Växla lager i en glob**

* Högerklicka i visualiseringen och klicka på önskat lagernamn. Ett X till vänster om lagret anger att lagret är synligt.
