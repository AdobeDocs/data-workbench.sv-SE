---
description: Information om uppgradering och avinstallation av Report Server-programvara.
title: Uppgraderar och avinstallerar rapportservern
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Uppgraderar och avinstallerar rapportservern{#upgrading-and-uninstalling-report-server}

Information om uppgradering och avinstallation av Report Server-programvara.

* [Uppgraderar rapport](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [Avinstallerar rapport](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Uppgraderar rapportservern {#section-95fea4bddad74616a8aea450dcdb2282}

Om du uppgraderar till [!DNL Report Server] 5.4 kan du använda instruktionerna för att uppgradera din [!DNL Report Server]-programvara. Om du använder [!DNL Report Server] 3.6 eller tidigare kontaktar du Adobe för att få hjälp med uppgraderingen.

Om du vill uppgradera [!DNL Report Server] 5.4 använder du data workbench för att kopiera en uppgraderingsfil till den data workbench-server som [!DNL Report Server] ansluter till. Sedan uppgraderar [!DNL Report]-serverinstanser automatiskt sig själva när de ansluter till den servern och läser in en profil.

>[!NOTE]
>
>Innan du uppgraderar [!DNL Report Server] måste du se till att du har uppgraderat din data workbench-serverprogramvara samt de profiler som körs på data workbench-servern. Mer information får du av Adobe Consulting Services.

För att kunna utföra följande procedur måste du först skaffa uppgraderingsfilen för [!DNL Report Server].

**Så här uppgraderar du till  [!DNL Report Server] 5.4 och senare versioner**

1. Gör en säkerhetskopia av alla filer under [!DNL E:\Portal] och ta bort alla filer och mappar i den här katalogen.
1. Kopiera innehållet i den nya versionen till [!DNL E:\Portal].
1. Ändra [!DNL global.asa], [!DNL email.asp] och [!DNL TopNavigation.xml] enligt instruktionerna i föregående avsnitt.

1. Kopiera [!DNL users.mdb] från säkerhetskopian.

   >[!NOTE]
   >
   >Om du inte tidigare genererade rapporter med PNG-utdata måste du gå in i de enskilda rapportmapparna och ändra [!DNL reports.xml] så att det innehåller rapportformatet PNG. Annars kan du få ett 500-fel. Ditt ursprungliga [!DNL reports.xml] skulle se ut ungefär så här:

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

1. I [!DNL report.cfg] tar du med ett utdataformat för png och save. Framöver bör rapporter genereras i PNG-format.

**Att uppgradera till  [!DNL Report Server] 4.0**

1. På datorn med Data Workbench kopierar du uppgraderingsfilen för Report Server till mappen [!DNL Temp\Software] i den katalog där data workbench är installerad.
1. Starta data workbench och läs in profilen [!DNL Configuration].
1. Klicka på miniatyrbilden för **[!UICONTROL Configure Connection to Servers]**.
1. Högerklicka på serverikonen för data workbench i [!DNL Servers Manager] och klicka på **[!UICONTROL Server Files]**.

1. Öppna mappen [!DNL Report Server] i mappen Software.
1. Högerklicka på bockmarkeringen **[!UICONTROL Temp]** för [!DNL ReportServer.exe] och välj **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Avinstallerar rapportservern {#section-96eb3281c45a45c0a7065deaa6845c25}

**Avinstallera[!DNL Report Server]**

1. Avregistrera tjänsten [!DNL Report Windows].

   1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade data workbench-servern (InsightServer64.exe). Exempel: [!DNL D:\Adobe\Report\bin]
   1. Kör följande kommando i kommandotolken för att stoppa och avregistrera den som en tjänst i Microsoft Windows: [!DNL visualreport /unregserver]

1. Ta bort installationskatalogen för Report Server.
