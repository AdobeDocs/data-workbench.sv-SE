---
description: Du kan anpassa utseendet på menyer, inklusive arbetsytans fönstermeny (nås genom att högerklicka på en arbetsyta) och menyer med mått, dimensioner och kartlager.
solution: Analytics
title: Anpassa en meny
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Anpassa en meny{#customize-a-menu}

Du kan anpassa utseendet på menyer, inklusive arbetsytans fönstermeny (nås genom att högerklicka på en arbetsyta) och menyer med mått, dimensioner och kartlager.

Hierarkin för en meny speglar strukturen för dess katalog i [!DNL Profile Manager]. Arbetsytans fönstermeny speglar till exempel strukturen i Menu-katalogen och metrics-menyn speglar strukturen i Metrics-katalogen. För alla menyer kan motsvarande katalog innehålla följande alternativ:

* **Filer:** Dessa filer representerar de visualiseringar, förklaringar, anteckningar, administrativa gränssnitt, mått, dimensioner eller kartlager som du kan öppna genom att klicka på motsvarande menyalternativ.
* **En[!DNL order.txt]fil:** Den här filen anger i vilken ordning menyalternativen visas.
* **Underkataloger:** Varje underkatalog representerar en undermeny. Varje underkatalog kan innehålla egna filer, underkataloger och [!DNL order.txt] filer.

Menyn innehåller till exempel menyalternativen Metrisk, Färg, Värde och Förtroende i den ordningen. [!DNL Add Legend] Som en jämförelse innehåller katalogen Meny\Lägg till förklaring i [!DNL Profile Manager] filerna [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw]och [!DNL Value.vw] filerna i alfabetisk ordning samt en [!DNL order.txt] fil som styr ordningen på de andra filerna.
