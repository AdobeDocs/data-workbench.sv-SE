---
description: Instruktioner för att justera DPU-prestanda.
solution: Insight
title: Inställningar för DPU-prestanda
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Inställningar för DPU-prestanda{#dpu-performance-settings}

Instruktioner för att justera DPU-prestanda.

Fyll i följande parametrar i * [!DNL Insight Server] installationskatalogen*\Components\DPU.cfg.

| Parameter | Beskrivning |
|---|---|
| Antal körningsbatchar | Detta är en justeringsparameter. Standardvärdet är 65536. Du kan ange godtyckligt små antal körningsgrupper. Kontakta Adobe innan du gör några ändringar i detta värde. |
| Körningsgrupper | Detta är en justeringsparameter. Standardvärdet är 128. Kontakta Adobe innan du gör några ändringar i detta värde. |
| Körningstid | Detta är en justeringsparameter. Standardvärdet är 0,100. Kontakta Adobe innan du gör några ändringar i detta värde. |
| Fältdump vid fel | Den här parametern kan anges till true eller false. Om värdet är true [!DNL Insight Server] skapas en fil med namnet [!DNL Field Dump number.txt] i katalogen Trace när körningsmotorfel inträffar. &lt; [!DNL Field Dump] > [!DNL number][!DNL .txt] är användbart vid felsökning. |
| Profilsökväg | Plats där filer för alla profiler ska lagras. Standardplatsen är Profiler\. |
| Gräns för frågeminne | Mängd minne (i byte) som [!DNL Insight Server] reserveras för att lagra frågeresultat. Standardvärdet är 10000000 (100 MB.) Om mer utrymme krävs för frågeresultat (t.ex. för att tillåta fler samtidiga användare) kan inställningen ökas, men du måste fortsätta att kontrollera [!DNL Insight Server’s] minnesbelastningen. |
| Tillståndsbana | Plats för systemtillståndsfiler. Standardplatsen är Läge\. |
| Trådar | En prestandajusteringsparameter för [!DNL Insight Server] datorer med flera processorer. I allmänhet ska det här värdet anges till n för alla n-core-system. Standardvärdet är 1. |
| Användarsökväg | Plats för behöriga användares filer. Standardplatsen är Användare\. |

