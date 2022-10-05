---
description: Loggfiler (.vsl) innehåller fält med händelsedata som samlas in från servrar av sensorer och som används av data workbench-servern i datauppsättningsprocessen.
title: Händelsedatapostfält (.vsl-filer)
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Fält för händelsedatapost{#event-data-record-fields}

{{eol}}

Loggfiler (.vsl) innehåller fält med händelsedata som samlas in från servrar av sensorer och som används av data workbench-servern i datauppsättningsprocessen.

Namnen på fälten följer vanligtvis namnkonventionen för det utökade loggfilformatet W3C. Många av fälten har prefix som anger källan till informationen i fältet:

* &quot;cs&quot; indikerar kommunikation från klienten till servern
* &quot;sc&quot; anger kommunikation från servern till klienten
* &quot;s&quot; anger information från servern
* &quot;c&quot; anger information från klienten
* &quot;x&quot; anger information som har skapats av en Adobe-produkt
