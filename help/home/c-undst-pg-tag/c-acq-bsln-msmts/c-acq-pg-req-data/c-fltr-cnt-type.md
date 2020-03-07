---
description: Syftet med Sensorns filtreringsfunktion av innehållstyp är att eliminera behovet av att lagra och bearbeta information som inte är användbar i analyssyfte.
solution: Analytics
title: Filtrera efter innehållstyp
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtrera efter innehållstyp{#filtering-by-content-type}

Syftet med Sensorns filtreringsfunktion av innehållstyp är att eliminera behovet av att lagra och bearbeta information som inte är användbar i analyssyfte.

En stor del av de data som finns tillgängliga via webbserverns API är inte användbara vid affärsanalyser. Lagring och bearbetning är dyra och [!DNL Sensor’s] filtrering av innehållstyp gör att du kan undvika onödig lagring och bearbetning.

För att maximera databearbetningsprestanda för webbloggen och minska mängden mätdata som måste lagras, [!DNL Site] hämtas mätdata (begärandedata, loggposter, loggdata o.s.v.) för alla typer av webbinnehåll, utom för specifikt listade innehållstyper (t.ex. CSS, bildförfrågningar o.s.v.) som filtreras ut innan de överförs till data workbench-servern av [!DNL Sensor]. Den här filtreringen kan inaktiveras för en hel webbserver och kan även åsidosättas för ett visst innehållsobjekt genom att lägga till namnvärdespar &quot;Log=1&quot; i frågesträngen för ett visst inbäddat objekt (till exempel [!DNL http://www.mysite.com/advertisement.gif?Log=1]).
