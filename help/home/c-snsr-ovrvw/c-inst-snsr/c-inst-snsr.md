---
description: Du installerar sensor på samma dator som den server vars aktivitet du vill mäta.
title: Installera sensor
uuid: 8d500fd0-daa0-453b-8284-b3f112a358ce
exl-id: cd5b54bf-301a-41a9-a69c-d9adb314be03
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Installerar sensor{#installing-sensor}

Du installerar sensor på samma dator som den server vars aktivitet du vill mäta.

Varje server som du vill hämta händelsedata från måste köra [!DNL Sensor].

[!DNL Sensor] kan installeras på en mängd olika webb- och programservrar som stöds eller på specialiserade datainsamlingsservrar som används för att hämta information från sidor, annonser och andra Internet-objekt som har taggats för mätning.

>[!NOTE]
>
>[!DNL Sensor] försämrar inte prestanda för en korrekt konfigurerad webb-, program- eller datainsamlingsserver.

Adobe har utformat [!DNL Sensor] för att stödja en växande familj av webbservrar och J2EE-servrar, inklusive men inte begränsat till AOLServer, Apache, iPlanet, JBoss, Microsoft IIS, Netscape Enterprise, Tomcat och Weblogic som körs i vanliga operativsystem, inklusive, men inte begränsat till, Microsoft Windows, AIX, Linux och Solaris. [!DNL Sensor’s] Med modulär arkitektur kan Adobe snabbt skapa ny datainhämtningslogik för andra applikationer efter behov.

Det här kapitlet innehåller procedurer för installation av [!DNL Sensor] för kombinationer av webbservrar och operativsystem.

Om du inte redan har installerat [!DNL data workbench server] som samlar in data från [!DNL Sensor] måste du göra det innan du utför procedurerna i det här kapitlet.
