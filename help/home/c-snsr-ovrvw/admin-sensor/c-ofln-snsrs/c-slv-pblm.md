---
description: När en webbserver kopplas från på grund av ett fel är lösningen enkel och kräver en Data Workbench-användare med tillräcklig behörighet för att öppna filen Log Processing Mode.cfg och lägga till sensorns (t.ex. WEB2) ID i avsnittet Offline Sources.
solution: Insight
title: Lösa problemet
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lösa problemet{#solving-the-problem}

När en webbserver kopplas från på grund av ett fel är lösningen enkel och kräver en Data Workbench-användare med tillräcklig behörighet för att öppna filen Log Processing Mode.cfg och lägga till sensorns (t.ex. WEB2) ID i avsnittet Offline Sources.

I det här avsnittet av filen anges [!DNL data workbench server] att inga data från den här källan längre ska förväntas eftersom den i själva verket är offline.

>[!NOTE]
>
>Ändringen behöver inte utföras av någon Adobe-konsult. Alla som har behörighet att öppna [!DNL Log Processing Mode.cfg] filen kan göra den här ändringen.

Om WEB2 börjar skicka data igen, kommer källan att [!DNL data workbench server] anslutas igen och därefter justeras från och med så att den återspeglar den senaste gången den tar emot data från alla källor som den är medveten om. Med andra ord har nya data som kommer in i systemet företräde framför vad som skrivs i [!DNL Log Processing Mode.cfg file].

Om WEB2 kopplas från igen avbryts tidpunkten och du måste redigera [!DNL Log Processing Mode.cfg] filen igen även om den redan har WEB2 som offlinekälla. Detta är en artefakt av produktens utformning som överensstämmer med definitionen från och med: senaste gången systemet har data för alla kända källor.

När du lägger till fler webbservrar (WEB4, WEB5, WEB6) och de börjar skicka data till [!DNL data workbench server]servern behöver du inte göra något för att de nya källorna ska [!DNL data workbench server] kännas igen. Systemet blir helt enkelt medvetet om att data från dessa nya källor bör förväntas, vilket beskrivs ovan.
