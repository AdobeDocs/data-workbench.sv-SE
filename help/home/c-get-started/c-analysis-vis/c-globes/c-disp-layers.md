---
description: I profilen Geografi lagras en samling bildlager och filer.
solution: Analytics
title: Visa lager
topic: Data workbench
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visa lager{#display-layers}

I profilen Geografi lagras en samling bildlager och filer.

När du visar en glob kan du välja vilket av de tillgängliga lagren som ska visas för en viss analysuppgift:

* **Blå marmor 2 km:** Det här lagret visar hela världen. När det här lagret inte är markerat visas inte glob.
* **IP-koordinater:** Det här elementpunktslagret visar latitud och longitud för platserna i din datamängd baserat på besökarens IP-adresser.
* **Postnummer:** I det här lagret visas latitud- och longitudvärdena för platser i din datauppsättning baserat på en lista med USA:s ZIP-koder från Adobe. Uppslagsfilen innehåller [!DNL Zip Points.txt] de postnummer, latitud- och longituddata som ska visas, medan [!DNL Zip Points.layer] filen innehåller de konfigurationsparametrar som behövs för att visa dessa data på jorden. Båda dessa filer lagras i mappen Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Andra tillgängliga lagernamn:*** Varje lagernamn representerar en [!DNL .layer] fil som lagras i mappen Profiles\Geography\Maps folder, Profiler\IP Geo-location\Maps eller Profiles\IP Geo-intelligence\Maps i installationskatalogen för Insight Server.

>[!NOTE]
>
>Om du vill ha IP Geo-location- eller IP Geo-Intelligence-profilen måste du prenumerera på antingen IP Geo-location- eller IP Geo-Intelligence-datatjänsten.

Om du vill styra i vilken ordning lagren ska visas kan du använda en [!DNL order.txt] fil. Se [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Växla lager i en glob**

* Högerklicka i visualiseringen och klicka på önskat lagernamn. Ett X till vänster om lagret anger att lagret är synligt.

