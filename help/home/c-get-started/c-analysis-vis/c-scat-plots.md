---
description: Punktdiagram visar elementen i en datamängd (till exempel Sida eller Ort) i ett rutnät där x- och y-axlarna representerar olika mätvärden.
solution: Analytics
title: 2D-punktdiagram
topic: Data workbench
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 2D-punktdiagram{#d-scatter-plots}

Punktdiagram visar elementen i en datamängd (till exempel Sida eller Ort) i ett rutnät där x- och y-axlarna representerar olika mätvärden.

Punktdiagram kan vara användbara när du vill förstå förhållandet mellan ett stort antal olika objekt, med två olika mätvärden. I följande exempel visar spridningsytan varje stad med antalet besökare och respektive kvarhållningsgrad.

![](assets/vis_ScatterPlot_City.png)

Med punktdiagram kan du snabbt se avvikelser. Exempel: Salt Lake City har en högre kvarhållningsfrekvens än den genomsnittliga per besökare.

Punktdiagram kan också användas för att visa att data är konsekventa. I följande exempel visar punktritytan antalet besökare med sessioner med en viss längd.

![](assets/vis_ScatterPlot_SessionDuration.png)

Storleken på varje punkt på punktytan bestäms av radiemätningen. Standardradiemått skiljer sig för varje Adobe-program. I [!DNL Site]till exempel baseras radiemätningen på sessioner som standard. Du kan ändra radiemått så att punkterna i dina punktdiagram representerar alla tillgängliga mätvärden. Anvisningar om hur du gör det finns i [Ändra radiemätningar](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) . Punktens färg baseras på den färgförklaring som är öppen på arbetsytan. Mer information om färgförklaringar finns i [Färgförklaringar](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

## Markera punkter {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**Markera en punkt**

* Klicka på punkten.

**Lägga till ytterligare en punkt eller grupp med punkter i markeringen**

* Ctrl-klicka på en punkt eller Ctrl-dra över flera punkter.

**Ta bort en punkt eller en grupp punkter från markeringen**

* Skift+klicka på en punkt eller Skift+dra över flera punkter.

## Ändra dimensioner {#section-796cd962ef3f476caa89d99083782ed1}

* Högerklicka på måttets etikett högst upp i diagrammet och klicka på **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

## Ändra mätvärden {#section-44b8be9215cd4039b1eeb98ae1b31445}

**Ändra måtten som visas på x- eller y-axeln i ett punktdiagram**

* Högerklicka på etiketten för måttet som du vill ändra och klicka på **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*.

## Ändra radiemått {#section-fd80576d583c430cb469daf12e39aa2a}

**Ändra radiemått för en punktdiagram**

Högerklicka på måttets etikett högst upp i diagrammet och klicka på **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_ScatterPlot_Change.png)

