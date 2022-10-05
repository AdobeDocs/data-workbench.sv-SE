---
description: Rapportportalen består av en uppsättning ASP-filer (Application Server pages) och stödfiler.
title: Installera rapportportalprogramfiler
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Installera rapportportalprogramfiler{#install-the-report-portal-application-files}

{{eol}}

Rapportportalen består av en uppsättning ASP-filer (Application Server pages) och stödfiler.

Så här installerar du [!DNL Report Portal]måste du extrahera dessa filer från den distributionsfil som du fick från Adobe och installera dem på den dator där Microsoft IIS körs.

**Så här installerar du [!DNL Report Portal] programfiler**

1. Om du inte redan har gjort det hämtar du installationspaketet (.zip-fil) för [!DNL Report Portal] från Adobe FTP-sajten.
1. Extrahera filerna i installationspaketet till valfri plats på den dator där IIS körs. I det här steget installeras följande undermappar och filer i mappen VSVirtualPortalName.

   | Mapp eller fil | Beskrivning |
   |---|---|
   | [!DNL \data\users.mdb] | Databas som innehåller listan över behöriga [!DNL Report Portal] -användare. |
   | [!DNL \PortalASP\] | Mappen som innehåller ASP-filerna som utgör [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Mapp som innehåller fem undermappar (Core, CSS, HTC, Images och Output) som innehåller stödfiler som används av [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Konfigurationsfil som du använder för att definiera de virtuella kataloger som är associerade med [!DNL Report Portal] (används endast med IIS 6.0). |

   Katalogen ser ut som i följande exempel:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Namnet på katalogen kan skilja sig från namnet som visas i exemplet.

1. Byt namn på mappen VSVirtualPortalName (eller annat namn) till det du vill använda som virtuell rotkatalog för din [!DNL Report Portal] (nedan kallade *PortalName*). Mer information om virtuella kataloger finns i nästa avsnitt.
