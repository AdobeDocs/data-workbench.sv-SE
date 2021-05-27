---
description: Ändra parametern ExpPartialMatch (valfritt)
title: Ändra parametern ExpPartialMatch (valfritt)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 0%

---

# Ändra parametern ExpPartialMatch (valfritt){#modifying-the-exppartialmatch-parameter-optional}

Om du vill att dina kontrollerade experiment ska kunna mappa hela webbplatsen eller en hel underkatalog på webbplatsen till en annan plats, kan du ange parametern ExpPartialMatch i [!DNL txlogd.conf]-filen till &quot;on&quot;. Standardvärdet är &quot;off&quot;.

Här följer ett exempel på parametern ExpPartialMatch:

[!DNL ExpPartialMatch off]

Var mycket försiktig när du ställer in den här parametern på&quot;on&quot; eftersom det kan leda till oavsiktlig ommappning av hela webbplatsen.
