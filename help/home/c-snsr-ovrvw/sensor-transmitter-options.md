---
description: Information om startkommandon för Sensor-sändare för UNIX och Windows.
title: Kommandoradsalternativ för sensorsändare
uuid: 8d077d76-a709-494e-a176-07ca3e761662
exl-id: f4b27859-8fab-42cd-bad0-b32f87764668
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Kommandoradsalternativ för sensorsändare{#sensor-transmitter-command-line-options}

{{eol}}

Information om startkommandon för Sensor-sändare för UNIX och Windows.

## Startkommando för UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Använd följande kommando för att starta sensorsändaren på en UNIX-stam:

```
txlogd -f configFileName
```

där configFileName är det fullständiga, kvalificerade namnet på sändarens konfigurationsfil (txlogd.conf).

Som standard körs sändaren som en bakgrundsprocess (daemon) och skriver operativa meddelanden till syslog.

Här följer en fullständig lista över kommandoradsväxlar för txlog:

| Byt | Beskrivning |
|---|---|
| -f | Anger det fullständiga, kvalificerade namnet på konfigurationsfilen (txlogd.conf). Om du inte anger den här växeln söker sändaren efter txlogd.conf i den aktuella katalogen. |
| -n | Startar sändaren i interaktivt läge (inte som en bakgrundsprocess). |
| -i | Startar sändaren i interaktivt läge och dirigerar felsökningsutdata till stdout. |
| -d | Startar sändaren som en bakgrundsprocess och dirigerar felsökningsutdata till txlogd-debug.log i den aktuella katalogen. |
| -c | Startar sändaren och skapar diskköfilen om den inte finns. Om diskkön redan finns ignoreras den här parametern. |
| -x | Startar sändaren och gör att den avslutas när det sista paketet i diskkön har skickats. Du kan använda det här alternativet om du vill tömma kön som förberedelse för en administrativ åtgärd, som att skapa en ny köfil. |

## Startkommando för Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Om du vill starta sensorn och registrera den som en tjänst i ett Windows-system använder du följande kommando:

```
txlog /regserver
```
