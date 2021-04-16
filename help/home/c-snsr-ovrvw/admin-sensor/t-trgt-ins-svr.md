---
description: Om du vill ändra den data workbench-server som en sensor kommunicerar med (målservern) måste du redigera filen txlogd.conf på var och en av de webbservrar där Sensor är installerat.
title: Ändra målserverns Data Workbench
uuid: 931d376d-8622-4858-8290-19ce91538570
exl-id: 9d18cae1-4037-48c6-8514-3278e2c73b47
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Ändra målserverns Data Workbench{#changing-the-target-data-workbench-server}

Om du vill ändra den data workbench-server som en sensor kommunicerar med (målservern) måste du redigera filen txlogd.conf på var och en av de webbservrar där Sensor är installerat.

**Ändra till mål[!DNL data workbench server]**

1. Stoppa både den ursprungliga målservern och den nya målservern.
1. Kopiera den senaste [!DNL .vsl]-filen från den ursprungliga målservern till den nya målservern. När du startar om den nya målservern i ett senare steg läggs alla nya [!DNL Sensor]-data till i den aktuella, befintliga [!DNL .vsl]-filen i stället för att en ny [!DNL .vsl]-fil skapas. Gör så här:

   1. På den ursprungliga målservern bläddrar du till mappen [!DNL \Logs] i installationskatalogen för [!DNL data workbench server].

   1. Kopiera den senaste [!DNL .vsl]-filen i mappen.
   1. På den nya målservern bläddrar du till mappen [!DNL \Logs] i installationskatalogen [!DNL data workbench server] och klistrar in filen [!DNL .vsl] i den här mappen.

1. Öppna och redigera [!DNL txlogd.conf]-filen på en av de webbservrar där [!DNL Sensor] är installerad. Gör så här:

   1. Bläddra till installationskatalogen för [!DNL Sensor] och öppna filen [!DNL txlogd.conf] i en textredigerare.

   1. Leta reda på parametern ServerAddress och ändra den så att den återspeglar adressen för den nya målservern.
   1. Spara och stäng filen.

1. Upprepa steg 2-3 på alla återstående webbservrar där [!DNL Sensor] är installerat.
1. Starta om den ursprungliga målservern (om den fortfarande ska användas) och den nya målservern.
1. Data börjar överföra till den nya målservern som du har angett.
