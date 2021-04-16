---
description: Gränssnittet Detaljerad status i data workbench är användbart för felsökning av fel eller andra problem med Data Workbench Server- och Report Server-datorer som är Data Workbench Server-klienter.
title: Rapportserverstatus visas
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# Visa rapportserverstatus{#displaying-report-server-status}

Gränssnittet Detaljerad status i data workbench är användbart för felsökning av fel eller andra problem med Data Workbench Server- och Report Server-datorer som är Data Workbench Server-klienter.

Om du vill visa rapportens status i [!DNL Master Server Detailed Status]-gränssnittet måste du lägga till en rapportstatusserver i [!DNL Servers]-vektorn i [!DNL Communications.cfg]-filen för data workbench-servern. Följande procedur beskriver hur du lägger till rapportstatusservern i filen [!DNL Communications.cfg]:

Mer information om [!DNL Detailed Status]-gränssnitt finns i kapitlet Administrativa gränssnitt i *användarhandboken för Data Workbench*.

**Lägga till en[!DNL Report Status Server]**

1. Navigera till mappen Komponenter i den katalog där du installerade data workbench-servern (InsightServer64.exe.)

   Exempel: [!DNL C:\Adobe\Server\Components]
1. Öppna [!DNL Communications.cfg] i en textredigerare som Anteckningar.
1. Leta reda på vektorn [!DNL Servers] och lägg till rapportstatusservern i den här vektorn så som den markeras i följande filfragment.

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

1. Uppdatera antalet objekt för [!DNL Servers]-vektorn (d.v.s. ökar objektvärdet med ett) så som det markerats i filfragmentet i föregående steg.
1. Spara filen.
