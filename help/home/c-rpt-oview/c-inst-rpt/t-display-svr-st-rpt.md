---
description: Gränssnittet Detaljerad status i data workbench är användbart för felsökning av fel eller andra problem med Data Workbench Server- och Report Server-datorer som är Data Workbench Server-klienter.
title: Rapportserverstatus visas
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# Rapportserverstatus visas{#displaying-report-server-status}

{{eol}}

Gränssnittet Detaljerad status i data workbench är användbart för felsökning av fel eller andra problem med Data Workbench Server- och Report Server-datorer som är Data Workbench Server-klienter.

Så här visar du rapportens status i [!DNL Master Server Detailed Status] -gränssnittet måste du lägga till en rapportstatusserver i [!DNL Servers] vektor i data workbench-serverns [!DNL Communications.cfg] -fil. I proceduren nedan beskrivs hur du lägger till rapportstatusservern i [!DNL Communications.cfg] fil:

Mer information om [!DNL Detailed Status] gränssnitt, se kapitlet Administrativa gränssnitt i *Användarhandbok för Data Workbench*.

**Lägga till en[!DNL Report Status Server]**

1. Navigera till mappen Komponenter i den katalog där du installerade data workbench-servern (InsightServer64.exe.)

   Exempel: [!DNL C:\Adobe\Server\Components]
1. Öppna [!DNL Communications.cfg] i en textredigerare som Anteckningar.
1. Leta reda på [!DNL Servers] vektor och lägg till rapportstatusservern i den här vektorn, vilket markeras i följande filfragment.

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. Uppdatera antalet artiklar för [!DNL Servers] vektor (d.v.s. ökar objektvärdet med ett) så som den markeras i filfragmentet i föregående steg.
1. Spara filen.
