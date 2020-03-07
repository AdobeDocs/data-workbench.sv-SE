---
description: Rapportportalen består av en uppsättning ASP-filer (Application Server pages) och stödfiler.
solution: Analytics
title: Installera rapportportalprogramfiler
topic: Data workbench
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installera rapportportalprogramfiler{#install-the-report-portal-application-files}

Rapportportalen består av en uppsättning ASP-filer (Application Server pages) och stödfiler.

Om du vill installera [!DNL Report Portal]filen måste du extrahera de här filerna från distributionsfilen som du har fått från Adobe och installera dem på den dator där Microsoft IIS körs.

**Installera[!DNL Report Portal]programfilerna**

1. Om du inte redan har gjort det hämtar du installationspaketet (.zip-fil) för [!DNL Report Portal] från Adobes FTP-plats.
1. Extrahera filerna i installationspaketet till valfri plats på den dator där IIS körs. I det här steget installeras följande undermappar och filer i mappen VSVirtualPortalName.

   | Mapp eller fil | Beskrivning |
   |---|---|
   | [!DNL \data\users.mdb] | Databas som innehåller listan över behöriga [!DNL Report Portal] användare. |
   | [!DNL \PortalASP\] | Mapp som innehåller de ASP-filer som ingår [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Mappen innehåller fem undermappar (Core, CSS, HTC, Images och Output) som innehåller stödfiler som används av [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Konfigurationsfil som du använder för att definiera de virtuella kataloger som är associerade med [!DNL Report Portal] (används endast med IIS 6.0). |

   Katalogen ser ut som i följande exempel:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Namnet på katalogen kan skilja sig från namnet som visas i exemplet.

1. Byt namn på mappen VSVirtualPortalName (eller annat namn) till det du vill använda som virtuell rotkatalog för din [!DNL Report Portal] (kallas nedan *PortalName*). Mer information om virtuella kataloger finns i nästa avsnitt.
