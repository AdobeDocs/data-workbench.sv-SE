---
description: Data workbench Geography stöder både latitud- och longitudprojektioner och UTM-projektioner (Universal Transverse Mercator) för alla terrängbildslagerkällor.
title: Ange projektionsinformation för terrängbilder
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%

---

# Ange projektionsinformation för terrängbilder{#specifying-projection-information-for-terrain-images}

Data workbench Geography stöder både latitud- och longitudprojektioner och UTM-projektioner (Universal Transverse Mercator) för alla terrängbildslagerkällor.

Projektionsinformation krävs för oprojicerade oprojicerade bitmappar och allmänna bilder, utan projicering. Du kan ange projektionsinformation för bilder med inbäddad projektionsinformation, men det är vanligtvis inte nödvändigt eftersom projektionsparametrarna bestäms automatiskt utifrån geodetiska data som är inbäddade i själva bilden. Följande avsnitt innehåller information om hur du anger dessa projektionsformat i [!DNL Terrain Images.cfg]-filen.
