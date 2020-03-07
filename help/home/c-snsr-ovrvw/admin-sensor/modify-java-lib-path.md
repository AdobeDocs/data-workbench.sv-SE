---
description: Instruktioner för att lägga till visual_Sciences.dll i Tomcat java-bibliotekssökvägen.
title: Ändra sökvägen till Java-biblioteket
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändra sökvägen till Java-biblioteket{#modify-the-java-library-path}

Instruktioner för att lägga till visual_Sciences.dll i Tomcat java-bibliotekssökvägen.

1. Navigera till installationskatalogen för Tomcat på Windows-servern. (Tomcat > bin)
1. Kör Tomcat9w.exe (Common daemon service manager) under mappen bin.

Lägg till en ny rad under Java-alternativen på fliken Java:

```
-Djava.library.path=C:\Sensor directory
```

Där C:\Sensor directory is the directory containing the visual_sciences.dll fil.
