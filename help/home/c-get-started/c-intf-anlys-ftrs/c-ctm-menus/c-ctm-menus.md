---
description: Du kan anpassa utseendet på menyer, inklusive arbetsytans fönstermeny (nås genom att högerklicka på en arbetsyta) och menyer med mått, dimensioner och kartlager.
title: Anpassa en meny
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Anpassa en meny{#customize-a-menu}

Du kan anpassa utseendet på menyer, inklusive arbetsytans fönstermeny (nås genom att högerklicka på en arbetsyta) och menyer med mått, dimensioner och kartlager.

Hierarkin för en meny speglar strukturen för dess katalog i [!DNL Profile Manager]. Arbetsytans fönstermeny speglar till exempel strukturen i Menu-katalogen och metrics-menyn speglar strukturen i Metrics-katalogen. För alla menyer kan motsvarande katalog innehålla följande alternativ:

* **Filer:** Dessa filer representerar de visualiseringar, förklaringar, anteckningar, administrativa gränssnitt, mått, dimensioner eller kartlager som du kan öppna genom att klicka på motsvarande menyalternativ.
* **En  [!DNL order.txt] fil:** Den här filen anger i vilken ordning menyalternativen visas.
* **Underkataloger:** Varje underkatalog representerar en undermeny. Varje underkatalog kan innehålla egna filer, underkataloger och [!DNL order.txt]-fil.

Menyn [!DNL Add Legend] innehåller menyalternativen Metrisk, Färg, Värde och Förtroende i den ordningen. Som en jämförelse innehåller katalogen Menu\Add Legend i [!DNL Profile Manager] filerna [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw] och [!DNL Value.vw] i alfabetisk ordning samt en [!DNL order.txt]-fil som styr ordningen på de andra filerna.
