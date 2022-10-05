---
description: När en webbserver kopplas från på grund av ett fel är Datan Workbench en enkel lösning som kräver att en användare med tillräcklig behörighet öppnar filen Log Processing Mode.cfg och lägger till sensorns (t.ex. WEB2) ID i avsnittet Offline Sources.
title: Lösa problemet
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Lösa problemet{#solving-the-problem}

{{eol}}

När en webbserver kopplas från på grund av ett fel är Datan Workbench en enkel lösning som kräver att en användare med tillräcklig behörighet öppnar filen Log Processing Mode.cfg och lägger till sensorns (t.ex. WEB2) ID i avsnittet Offline Sources.

Det här avsnittet av filen innehåller information om [!DNL data workbench server] att de inte längre ska förvänta sig data från den här källan, eftersom den i själva verket är offline.

>[!NOTE]
>
>Denna ändring behöver inte utföras av en konsult från Adobe. Alla som har behörighet att öppna [!DNL Log Processing Mode.cfg] filen kan göra den här ändringen.

Om WEB2 börjar skicka data igen [!DNL data workbench server] återställer källan online och justerar tidpunkten så att den återspeglar den senaste gången den tar emot data från alla källor som den är medveten om. Med andra ord har nya data som kommer in i systemet företräde framför det som skrivs i [!DNL Log Processing Mode.cfg file].

Om WEB2 kopplas från igen avbryts funktionen från och med igen och du måste redigera [!DNL Log Processing Mode.cfg] filen igen även om den redan har WEB2 som offlinekälla. Detta är en artefakt av produktens utformning som överensstämmer med definitionen från och med: senaste gången systemet har data för alla kända källor.

När du lägger till fler webbservrar (WEB4, WEB5, WEB6) och de börjar skicka data till [!DNL data workbench server]behöver du inte göra något för att ha [!DNL data workbench server] känner igen de nya källorna. Systemet blir helt enkelt medvetet om att data från dessa nya källor bör förväntas, vilket beskrivs ovan.
