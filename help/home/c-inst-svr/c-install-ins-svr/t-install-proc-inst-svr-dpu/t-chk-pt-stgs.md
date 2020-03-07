---
description: Insight Server lyssnar som standard på port 80 (för HTTP) och 443 (för HTTPS).
solution: Insight
title: Kontrollera portinställningarna
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Kontrollera portinställningarna{#checking-the-port-settings}

Insight Server lyssnar som standard på port 80 (för HTTP) och 443 (för HTTPS).

Om portarna redan har tilldelats av en annan process på den dator där du har installerat [!DNL Insight Server]gör du så här för att ändra [!DNL Insight Server’s] porttilldelningar.

**Ändra porttilldelningar**

1. Navigera till mappen [!DNL Components] i den katalog där du installerade [!DNL Insight Server].

   Exempel: [!DNL C:\Adobe\Server\Components]

1. Öppna [!DNL Communications.cfg] filen i en textredigerare som Anteckningar.
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

1. Om detta inte är de portar som du vill [!DNL Insight Server] använda ändrar du porttilldelningarna och sparar och stänger sedan filen.
