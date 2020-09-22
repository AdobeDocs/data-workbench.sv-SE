---
description: När en webbserver kopplas från på grund av ett fel är Datan Workbench en enkel lösning som kräver att en användare med tillräcklig behörighet öppnar filen Log Processing Mode.cfg och lägger till sensorns (t.ex. WEB2) ID i avsnittet Offline Sources.
solution: Analytics
title: Lösa problemet
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---


# Lösa problemet{#solving-the-problem}

När en webbserver kopplas från på grund av ett fel är Datan Workbench en enkel lösning som kräver att en användare med tillräcklig behörighet öppnar filen Log Processing Mode.cfg och lägger till sensorns (t.ex. WEB2) ID i avsnittet Offline Sources.

I det här avsnittet av filen anges [!DNL data workbench server] att inga data från den här källan längre ska förväntas eftersom den i själva verket är offline.

>[!NOTE]
>
>Denna ändring behöver inte utföras av en konsult från Adobe. Alla som har behörighet att öppna [!DNL Log Processing Mode.cfg] filen kan göra den här ändringen.

Om WEB2 börjar skicka data igen, kommer källan att [!DNL data workbench server] anslutas igen och därefter justeras från och med så att den återspeglar den senaste gången den tar emot data från alla källor som den är medveten om. Med andra ord har nya data som kommer in i systemet företräde framför vad som skrivs i [!DNL Log Processing Mode.cfg file].

Om WEB2 kopplas från igen avbryts tidpunkten och du måste redigera [!DNL Log Processing Mode.cfg] filen igen även om den redan har WEB2 som offlinekälla. Detta är en artefakt av produktens utformning som överensstämmer med definitionen från och med: senaste gången systemet har data för alla kända källor.

När du lägger till fler webbservrar (WEB4, WEB5, WEB6) och de börjar skicka data till [!DNL data workbench server]servern behöver du inte göra något för att de nya källorna ska [!DNL data workbench server] kännas igen. Systemet blir helt enkelt medvetet om att data från dessa nya källor bör förväntas, vilket beskrivs ovan.
