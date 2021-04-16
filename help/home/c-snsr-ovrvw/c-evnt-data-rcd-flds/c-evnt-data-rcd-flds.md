---
description: Loggfiler (.vsl) innehåller fält med händelsedata som samlas in från servrar av sensorer och som används av data workbench-servern i datauppsättningsprocessen.
title: Fält för händelsedatapost
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 0%

---

# Händelsedatapostfält{#event-data-record-fields}

Loggfiler (.vsl) innehåller fält med händelsedata som samlas in från servrar av sensorer och som används av data workbench-servern i datauppsättningsprocessen.

Namnen på fälten följer vanligtvis namnkonventionen för det utökade loggfilformatet W3C. Många av fälten har prefix som anger källan till informationen i fältet:

* &quot;cs&quot; indikerar kommunikation från klienten till servern
* &quot;sc&quot; anger kommunikation från servern till klienten
* &quot;s&quot; anger information från servern
* &quot;c&quot; anger information från klienten
* &quot;x&quot; anger information som har skapats av en Adobe-produkt
