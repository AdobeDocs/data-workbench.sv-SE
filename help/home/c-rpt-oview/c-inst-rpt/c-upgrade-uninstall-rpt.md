---
description: Information om uppgradering och avinstallation av Report Server-programvara.
title: Uppgraderar och avinstallerar rapportservern
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Uppgraderar och avinstallerar rapportservern{#upgrading-and-uninstalling-report-server}

{{eol}}

Information om uppgradering och avinstallation av Report Server-programvara.

* [Uppgraderar rapport](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Avinstallerar rapport](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Uppgraderar rapportserver {#section-95fea4bddad74616a8aea450dcdb2282}

Om du uppgraderar till [!DNL Report Server] 5.4 Följ instruktionerna för att uppgradera [!DNL Report Server] program. Om du använder [!DNL Report Server] 3.6 eller tidigare, kontakta Adobe för att få hjälp med uppgraderingen.

Att uppgradera [!DNL Report Server] 5.4 använda data workbench för att kopiera en uppgraderingsfil till data workbench-servern som [!DNL Report Server] anslutningar. Efter att ha gjort det [!DNL Report] Serverinstanser uppgraderar sig automatiskt när de ansluter till den servern och läser in en profil.

>[!NOTE]
>
>Före uppgradering [!DNL Report Server]Kontrollera att du har uppgraderat din data workbench-serverprogramvara samt de profiler som körs på data workbench-servern. Mer information får du av Adobe Consulting Services.

För att kunna utföra följande procedur måste du först skaffa uppgraderingsfilen för [!DNL Report Server].

**Om du vill uppgradera till [!DNL Report Server] 5.4 och senare versioner**

1. Säkerhetskopiera alla filer under [!DNL E:\Portal] och ta bort alla filer och mappar i den här katalogen.
1. Kopiera innehållet i den nya versionen till [!DNL E:\Portal].
1. Ändra [!DNL global.asa], [!DNL email.asp]och [!DNL TopNavigation.xml] enligt instruktionerna i föregående avsnitt.

1. Kopiera [!DNL users.mdb] från din säkerhetskopia.

   >[!NOTE]
   >
   >Om du inte tidigare har genererat rapporter med PNG-utdata måste du gå till de enskilda rapportmapparna och ändra [!DNL reports.xml] för att inkludera ett rapportformat för png. Annars kan du få ett 500-fel. Originalet [!DNL reports.xml] skulle se ut ungefär så här:

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   Den skulle behöva ändras till följande:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. I [!DNL report.cfg], innehåller ett utdataformat för png och save. Framöver bör rapporter genereras i PNG-format.

**Om du vill uppgradera till [!DNL Report Server] 4.0**

1. På datorn med Data Workbench kopierar du uppgraderingsfilen för Report Server till [!DNL Temp\Software] i den katalog där data workbench är installerad.
1. Starta data workbench och läs in [!DNL Configuration] profil.
1. Klicka på **[!UICONTROL Configure Connection to Servers]** miniatyrbild.
1. I [!DNL Servers Manager], högerklicka på serverikonen för data workbench och klicka på **[!UICONTROL Server Files]**.

1. Öppna mappen Software [!DNL Report Server] mapp.
1. Högerklicka på **[!UICONTROL Temp]** bock för [!DNL ReportServer.exe] och markera **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Rapportservern avinstalleras {#section-96eb3281c45a45c0a7065deaa6845c25}

**Avinstallera[!DNL Report Server]**

1. Avregistrera [!DNL Report Windows] service.

   1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade data workbench-servern (InsightServer64.exe). Exempel: [!DNL D:\Adobe\Report\bin]
   1. Kör följande kommando i kommandotolken för att stoppa och avregistrera den som en tjänst i Microsoft Windows: [!DNL visualreport /unregserver]

1. Ta bort installationskatalogen för Report Server.
