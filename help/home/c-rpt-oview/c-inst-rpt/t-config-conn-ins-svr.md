---
description: Innan du kan generera rapporter och varningar måste du konfigurera Report Server så att adressen till Insight-servern anges och de profiler som du vill att den ska rapportera till identifieras.
title: Konfigurera anslutningen till Insight Server
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# Konfigurera anslutningen till Insight Server{#configuring-the-connection-to-the-insight-server}

Innan du kan generera rapporter och varningar måste du konfigurera Report Server så att adressen till Insight-servern anges och de profiler som du vill att den ska rapportera till identifieras.

>[!NOTE]
>
>Du kan inte köra Report Server korrekt förrän du har konfigurerat Report Server enligt beskrivningen nedan. Om du försöker köra Report Server med den okonfigurerade filen som är installerad med programmet genererar Report Server en ström med fel.

**Så här konfigurerar du rapportservern**

1. I Utforskaren i Windows navigerar du till katalogen där du installerade Report Server.
1. Öppna filen [!DNL ReportServer.cfg] i Anteckningar och ändra filen efter behov.

   Följande exempel [!DNL Report Server.cfg] innehåller bara de parametrar som ingår i [!DNL Report Server.cfg]-filen som standard (och markerar de parameterinställningar som krävs). Om du kontaktar Adobe licensserver via en proxyserver måste du lägga till licensvektorn och dess parametrar. Mer information finns i [Report Server.cfg parameters](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06).

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. Spara och stäng filen.
