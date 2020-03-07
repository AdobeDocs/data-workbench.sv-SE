---
description: Om du vill ändra den data workbench-server som en sensor kommunicerar med (målservern) måste du redigera filen txlogd.conf på var och en av de webbservrar där Sensor är installerat.
solution: Insight
title: Ändra måldata för Workbench-servern
uuid: 931d376d-8622-4858-8290-19ce91538570
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändra måldata för Workbench-servern{#changing-the-target-data-workbench-server}

Om du vill ändra den data workbench-server som en sensor kommunicerar med (målservern) måste du redigera filen txlogd.conf på var och en av de webbservrar där Sensor är installerat.

**Ändra till mål[!DNL data workbench server]**

1. Stoppa både den ursprungliga målservern och den nya målservern.
1. Kopiera den senaste [!DNL .vsl] filen från den ursprungliga målservern till den nya målservern. När du startar om den nya målservern i ett senare steg läggs alla nya [!DNL Sensor] data till i den aktuella befintliga [!DNL .vsl] filen i stället för att en ny [!DNL .vsl] fil skapas. Gör så här:

   1. På den ursprungliga målservern bläddrar du till [!DNL \Logs] mappen i [!DNL data workbench server] installationskatalogen.

   1. Kopiera den senaste [!DNL .vsl] filen i mappen.
   1. På den nya målservern bläddrar du till [!DNL \Logs] mappen i [!DNL data workbench server] installationskatalogen och klistrar in [!DNL .vsl] filen i den här mappen.

1. Öppna och redigera [!DNL Sensor] filen på någon av de webbservrar där [!DNL txlogd.conf] den är installerad. Gör så här:

   1. Bläddra till [!DNL Sensor] installationskatalogen och öppna [!DNL txlogd.conf] filen i en textredigerare.

   1. Leta reda på parametern ServerAddress och ändra den så att den återspeglar adressen för den nya målservern.
   1. Spara och stäng filen.

1. Upprepa steg 2-3 på alla återstående webbservrar som [!DNL Sensor] är installerade på.
1. Starta om den ursprungliga målservern (om den fortfarande ska användas) och den nya målservern.
1. Data börjar överföra till den nya målservern som du har angett.
