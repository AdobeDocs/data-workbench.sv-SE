---
description: Du kan anpassa utseendet på menyer, inklusive arbetsytans fönstermeny (nås genom att högerklicka på en arbetsyta) och menyer med mått, dimensioner och kartlager.
title: Anpassa en meny
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Anpassa en meny{#customize-a-menu}

{{eol}}

Du kan anpassa utseendet på menyer, inklusive arbetsytans fönstermeny (nås genom att högerklicka på en arbetsyta) och menyer med mått, dimensioner och kartlager.

Hierarkin för en meny speglar strukturen för dess katalog i [!DNL Profile Manager]. Arbetsytans fönstermeny speglar till exempel strukturen i Menu-katalogen och metrics-menyn speglar strukturen i Metrics-katalogen. För alla menyer kan motsvarande katalog innehålla följande alternativ:

* **Filer:** Dessa filer representerar de visualiseringar, förklaringar, anteckningar, administrativa gränssnitt, mått, dimensioner eller kartlager som du kan öppna genom att klicka på motsvarande menyalternativ.
* **An [!DNL order.txt] fil:** Den här filen anger i vilken ordning menyalternativen visas.
* **Underkataloger:** Varje underkatalog representerar en undermeny. Varje underkatalog kan innehålla egna filer, underkataloger och [!DNL order.txt] -fil.

Till exempel [!DNL Add Legend] -menyn innehåller menyalternativen Metrisk, Färg, Värde och Förtroende i den ordningen. Som en jämförelse finns katalogen Menu\Add Legend i [!DNL Profile Manager] innehåller filerna [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]och [!DNL Value.vw] filer i alfabetisk ordning, samt [!DNL order.txt] för att styra ordningen på de andra filerna.
