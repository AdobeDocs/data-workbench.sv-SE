---
description: Om du inte har behörighet att ta bort filer från en profil eller om du inte vill ta bort en fil permanent, kan du använda tomma (nollbyte) filer för att dölja filer.
solution: Analytics
title: Dölja en fil genom att tömma den (nollbyte)
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dölja en fil genom att tömma den (nollbyte){#hide-a-file-by-emptying-it-zero-byte}

Om du inte har behörighet att ta bort filer från en profil eller om du inte vill ta bort en fil permanent, kan du använda tomma (nollbyte) filer för att dölja filer.

I [!DNL Profile Manager]kolumnen används ett bindestreck (-) i stället för en bockmarkering för att identifiera en nollbytefil.

![](assets/vis_ProfMgr_Zero-byte.png)

Till skillnad från andra metoder för att dölja filer (t.ex. [!DNL order.txt]parametern Visa och parametern Dold) hanterar Data Workbench nollbyte-filer som filer som inte finns. Om du till exempel har nollbyte för en dimension som har använts i en visualisering eller en metrisk definition, genereras ett fel för visualiseringen respektive mätvärdena i Data Workbench.

Den här funktionen är användbar av flera skäl, bland annat när du vill göra följande:

* **Gör en fil oanvändbar** i Data Workbench utan att behöva de profilbehörigheter som krävs för att ta bort filen.
* **Flytta ett mått, en dimension eller ett filter** till en annan plats utan att behöva de profilbehörigheter som krävs för att ta bort filen från den ursprungliga platsen.
* **Dölj menyalternativ.** Profilen har till exempel [!DNL Base] en [!DNL Metric Legend] definition i [!DNL Metric.vw] filen. Anta att ditt företag har skapat tre måttförklaringar som du vill ska visas på undermenyn Lägg till förklaring > Metrisk. Du kan nollbyte i [!DNL Base] [!DNL Metric.vw] profilfilen så att bara den nya undermenyn och tre nya måttteckenförklaringar visas.

**Så här döljer du en fil**

1. I [!DNL Profile Manager]öppnar du de mappar och undermappar som behövs för att leta reda på filen som du vill nollbyte för.
1. Högerklicka på bockmarkeringen bredvid filens namn och klicka på **[!UICONTROL Make Local]**.
1. Öppna den lokala filen och ta bort dess innehåll.
1. Spara och stäng filen.

