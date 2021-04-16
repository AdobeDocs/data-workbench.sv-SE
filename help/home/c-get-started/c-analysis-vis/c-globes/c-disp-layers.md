---
description: I profilen Geografi lagras en samling bildlager och filer.
title: Visa lager
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Visa lager{#display-layers}

I profilen Geografi lagras en samling bildlager och filer.

När du visar en glob kan du välja vilket av de tillgängliga lagren som ska visas för en viss analysuppgift:

* **Blå marmor 2 km:** Detta lager visar världen. När det här lagret inte är markerat visas inte glob.
* **IP-koordinater:** Det här elementpunktslagret visar latitud och longitud för platserna i datauppsättningen baserat på besökarens IP-adresser.
* **Zip-punkter:** Det här lagret visar latitud och longitud för platser i datauppsättningen baserat på en lista över USA:s ZIP-koder som tillhandahålls av Adobe. Uppslagsfilen [!DNL Zip Points.txt] innehåller de ZIP-koder, latitud- och longituddata som ska visas, medan filen [!DNL Zip Points.layer] innehåller de konfigurationsparametrar som behövs för att visa dessa data på jorden. Båda dessa filer lagras i mappen Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Andra tillgängliga lagernamn:*** Varje lagernamn representerar en  [!DNL .layer] fil som lagras i mappen Profiles\Geography\Maps folder, Profiler\IP Geo-location\Maps eller Profiles\IP Geo-Intelligence\Maps i installationskatalogen för Insight Server.

>[!NOTE]
>
>Om du vill ha IP Geo-location- eller IP Geo-Intelligence-profilen måste du prenumerera på antingen IP Geo-location- eller IP Geo-Intelligence-datatjänsten.

Du kan styra i vilken ordning lagren ska visas genom att använda en [!DNL order.txt]-fil. Se [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Växla lager i en glob**

* Högerklicka i visualiseringen och klicka på önskat lagernamn. Ett X till vänster om lagret anger att lagret är synligt.
