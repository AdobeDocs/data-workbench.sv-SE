---
description: Syftet med Sensorns filtreringsfunktion av innehållstyp är att eliminera behovet av att lagra och bearbeta information som inte är användbar i analyssyfte.
title: Filtrera efter innehållstyp
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# Filtrera efter innehållstyp{#filtering-by-content-type}

{{eol}}

Syftet med Sensorns filtreringsfunktion av innehållstyp är att eliminera behovet av att lagra och bearbeta information som inte är användbar i analyssyfte.

En stor del av de data som finns tillgängliga via webbserverns API är inte användbara vid affärsanalyser. Lagring och bearbetning är dyra och [!DNL Sensor’s] filtrering av innehållstyper gör att du kan undvika onödig lagring och bearbetning.

För att maximera databearbetningsprestanda för webbloggen och minska mängden mätdata som måste lagras, [!DNL Site] hämtar mätdata (begärandedata, loggposter, loggdata o.s.v.) för alla webbinnehållstypbegäranden, utom för specifikt listade innehållstyper (som CSS, bildbegäranden o.s.v.) som filtreras ut innan de överförs till data workbench-servern av [!DNL Sensor]. Den här filtreringen kan inaktiveras för en hel webbserver och kan även åsidosättas för ett visst innehållsobjekt genom att lägga till namnvärdespar &quot;Log=1&quot; i frågesträngen för ett visst inbäddat objekt (till exempel [!DNL https://www.mysite.com/advertisement.gif?Log=1]).
