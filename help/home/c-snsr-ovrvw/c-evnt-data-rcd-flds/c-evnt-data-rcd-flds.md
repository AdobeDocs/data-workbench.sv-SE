---
description: Loggfiler (.vsl) innehåller fält med händelsedata som samlas in från servrar av sensorer och som används av data workbench-servern i datauppsättningsprocessen.
solution: Analytics
title: Fält för händelsedatapost
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 0%

---


# Fält för händelsedatapost{#event-data-record-fields}

Loggfiler (.vsl) innehåller fält med händelsedata som samlas in från servrar av sensorer och som används av data workbench-servern i datauppsättningsprocessen.

Namnen på fälten följer vanligtvis namnkonventionen för det utökade loggfilformatet W3C. Många av fälten har prefix som anger källan till informationen i fältet:

* &quot;cs&quot; indikerar kommunikation från klienten till servern
* &quot;sc&quot; anger kommunikation från servern till klienten
* &quot;s&quot; anger information från servern
* &quot;c&quot; anger information från klienten
* &quot;x&quot; anger information som har skapats av en Adobe-produkt

