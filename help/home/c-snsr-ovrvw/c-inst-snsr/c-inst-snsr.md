---
description: Du installerar sensor på samma dator som den server vars aktivitet du vill mäta.
title: Installera sensor
uuid: 8d500fd0-daa0-453b-8284-b3f112a358ce
exl-id: cd5b54bf-301a-41a9-a69c-d9adb314be03
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Installera sensor{#installing-sensor}

{{eol}}

Du installerar sensor på samma dator som den server vars aktivitet du vill mäta.

Varje server som du vill hämta händelsedata från måste köras [!DNL Sensor].

[!DNL Sensor] kan installeras på en mängd olika webb- och programservrar som stöds eller på specialiserade datainsamlingsservrar som används för att hämta information från sidor, annonser och andra Internet-objekt som har taggats för mätning.

>[!NOTE]
>
>[!DNL Sensor] försämrar inte prestanda för en korrekt konfigurerad webb-, program- eller datainsamlingsserver.

Adobe har designat [!DNL Sensor] för att stödja en växande familj av webbservrar och J2EE-applikationsservrar, inklusive men inte begränsat till AOLServer, Apache, iPlanet, JBoss, Microsoft IIS, Netscape Enterprise, Tomcat och Weblogic som körs på vanliga operativsystem, inklusive, men inte begränsat till, Microsoft Windows, AIX, Linux och Solaris. [!DNL Sensor’s] Med modulär arkitektur kan Adobe snabbt skapa ny datainhämtningslogik för andra applikationer efter behov.

Det här kapitlet innehåller procedurer för installation [!DNL Sensor] för kombinationer av webbservrar och operativsystem.

Om du inte redan har installerat [!DNL data workbench server] som samlar in data från [!DNL Sensor]måste du göra det innan du utför procedurerna i det här kapitlet.
