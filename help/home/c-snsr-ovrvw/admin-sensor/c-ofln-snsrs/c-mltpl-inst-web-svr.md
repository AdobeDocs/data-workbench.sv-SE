---
description: Information om den allmänna konfigurationen av sensorn med en webbserverinstans som körs på en webbserver.
title: Arbeta med flera instanser av en webbserver
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
exl-id: a371f9ed-6c27-4b3d-843f-ae5621013410
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Arbeta med flera instanser av en webbserver{#working-with-multiple-instances-of-a-web-server}

Information om den allmänna konfigurationen av sensorn med en webbserverinstans som körs på en webbserver.

![](assets/web_inst.png)

I det här scenariot skriver en enda webbserverinstans data till den minnesmappade köfilen, som läses av sändaren och skickas till [!DNL data workbench server].

När [!DNL Sensor] är installerat på en webbserver som kör flera insamlarinstanser kan du konfigurera det på ett av två sätt:

* Du kan låta alla samlingsmoduler dela en köfil.

   När du använder en enda köfil blir hantering, konfiguration och administration något enklare eftersom själva arkitekturen är mindre komplex. Men med en enda köfil identifieras hela webbservern, oavsett antalet instanser, som WEB1.

* Du kan replikera arkitekturen ovan flera gånger och låta varje webbserverinstans ha en separat köfil.

   På så sätt kan du identifiera var och en av webbserverinstanserna unikt. Identifieringen av webbservern (och motsvarande SensorID i [!DNL Sensor]-konfigurationen) är med andra ord en funktion i den här konfigurationen.

I vilket fall som helst innehåller data fortfarande all värdnamnsinformation så att du kan skilja mellan [!DNL www.client.com], [!DNL www2.client.com] och så vidare. Den korrekta konfigurationen avgörs av analysmålen och om analytikerna behöver segmentera data baserat på en specifik instans som körs på en webbserver.

>[!NOTE]
>
>Denna typ av segmentering används vanligtvis endast vid operativ analys och ger inte mycket praktisk användning utanför det området.
