---
description: Insight Server lyssnar som standard på port 80 (för HTTP) och 443 (för HTTPS).
title: Kontrollera portinställningarna
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 0%

---

# Kontrollera portinställningarna{#checking-the-port-settings}

{{eol}}

Insight Server lyssnar som standard på port 80 (för HTTP) och 443 (för HTTPS).

Om portarna redan har tilldelats av en annan process på datorn där du har installerat [!DNL Insight Server]använder du följande procedur för att ändra [!DNL Insight Server’s] porttilldelningar.

**Ändra porttilldelningar**

1. Navigera till [!DNL Components] i den katalog där du installerade [!DNL Insight Server].

   Exempel: [!DNL C:\Adobe\Server\Components]

1. Öppna [!DNL Communications.cfg] i en textredigerare som Anteckningar.
1. Leta reda på port- och SSL-portposterna enligt nedan:

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. Om detta inte är de portar som du vill ha [!DNL Insight Server] ändra porttilldelningarna och sedan spara och stänga filen.
