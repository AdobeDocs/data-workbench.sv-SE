---
description: Instruktioner för att lägga till visual_Sciences.dll i Tomcat java-bibliotekssökvägen.
title: Ändra sökvägen till Java-biblioteket
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 0%

---

# Ändra sökvägen till Java-biblioteket{#modify-the-java-library-path}

{{eol}}

Instruktioner för att lägga till visual_Sciences.dll i Tomcat java-bibliotekssökvägen.

1. Navigera till installationskatalogen för Tomcat på Windows-servern. (Tomcat > bin)
1. Kör Tomcat9w.exe (Common daemon service manager) under mappen bin.

Lägg till en ny rad under Java-alternativen på fliken Java:

```
-Djava.library.path=C:\Sensor directory
```

Där C:\Sensor directory is the directory containing the visual_sciences.dll fil.
