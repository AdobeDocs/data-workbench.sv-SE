---
description: Om du vill ändra den data workbench-server som en sensor kommunicerar med (målservern) måste du redigera filen txlogd.conf på var och en av de webbservrar där Sensor är installerat.
title: Ändra målserverns Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Ändra målserverns Data Workbench{#changing-the-target-data-workbench-server}

{{eol}}

Om du vill ändra den data workbench-server som en sensor kommunicerar med (målservern) måste du redigera filen txlogd.conf på var och en av de webbservrar där Sensor är installerat.

**Ändra till mål[!DNL data workbench server]**

1. Stoppa både den ursprungliga målservern och den nya målservern.
1. Kopiera den senaste [!DNL .vsl] från den ursprungliga målservern till den nya målservern. När du startar om den nya målservern i ett senare steg, orsakar detta alla nya [!DNL Sensor] data som ska läggas till den aktuella, befintliga [!DNL .vsl] i stället för att skapa en ny [!DNL .vsl] -fil. Gör så här:

   1. På den ursprungliga målservern bläddrar du till [!DNL \Logs] i [!DNL data workbench server] installationskatalog.

   1. Kopiera den senaste [!DNL .vsl] i mappen.
   1. På den nya målservern bläddrar du till [!DNL \Logs] i [!DNL data workbench server] installationskatalogen och klistra in [!DNL .vsl] till den här mappen.

1. På en av webbservrarna som [!DNL Sensor] är installerat, öppnar och redigerar [!DNL txlogd.conf] -fil. Gör så här:

   1. Bläddra till [!DNL Sensor] installationskatalogen och öppna [!DNL txlogd.conf] i en textredigerare.

   1. Leta reda på parametern ServerAddress och ändra den så att den återspeglar adressen för den nya målservern.
   1. Spara och stäng filen.

1. Upprepa steg 2-3 på alla återstående webbservrar på vilka [!DNL Sensor] är installerat.
1. Starta om den ursprungliga målservern (om den fortfarande ska användas) och den nya målservern.
1. Data börjar överföra till den nya målservern som du har angett.
