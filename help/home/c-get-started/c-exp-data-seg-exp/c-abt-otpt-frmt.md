---
description: Riktlinjer för att ange utdataformat.
title: Utdataformat
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# Utdataformat{#output-format}

Riktlinjer för att ange utdataformat.

* Varje mått- eller dimensionsnamn måste börja och sluta med ett procenttecken (%).

   * %XYZ% anger elementet i dimension XYZ som motsvarar elementet för nivå. Ett fel genereras om dimensionen XYZ inte är en-till-en eller en-till-många med Nivå.
   * %=XYZ% anger värdet för metrisk formel eller metrisk formel XYZ för det angivna elementet för Nivå.

* Dimensioner som är två ord eller längre behöver inte understreck.
* Mätnamn som är två ord eller längre kräver understreck.

>[!NOTE]
>
>Om du håller ned Ctrl-tangenten och högerklickar i fältet [!DNL Output Format] visas ett [!DNL Insert menu]. Den här menyn innehåller en lista med specialtecken (t.ex. tabb) som ofta används som avgränsare.

Om du vill exportera sessionsvaraktighetsdata för ditt segment måste du skapa ett nytt mått baserat på sessionsvaraktighetsmåttet. Det nya måttet, som bara används med fältet [!DNL Output Format] för segmentexport, gör att Microsoft Excel kan tolka sessioner som varar mindre än en timme. Om du vill skapa ett nytt mått för sessionens varaktighet öppnar du filen [!DNL Session Duration.metric] (från [!DNL Profile Manager]) och infogar ett nummertecken (#) i tidssträngen: [!DNL ftime = string: %#H:%M:%S]

Tvinga-tecknet gör att inledande &quot;0&quot; läggs till i sessionsvaraktigheter på mindre än 1 timme. Därför tolkas 0:53:21 som 53 minuter och 21 sekunder. Spara det nya måttet med ett annat namn och överför det till rätt profil som andra kan använda genom att högerklicka på bockmarkeringen för filen i kolumnen [!DNL User] och klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
