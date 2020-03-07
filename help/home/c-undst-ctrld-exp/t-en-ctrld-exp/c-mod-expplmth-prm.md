---
description: 'null'
solution: Insight,Analytics
title: Ändra parametern ExpPartialMatch (valfritt)
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändra parametern ExpPartialMatch (valfritt){#modifying-the-exppartialmatch-parameter-optional}

Om du vill att dina kontrollerade experiment ska kunna mappa hela webbplatsen eller en hel underkatalog på webbplatsen till en annan plats, kan du ange parametern ExpPartialMatch i [!DNL txlogd.conf] filen till &quot;on&quot;. Standardvärdet är &quot;off&quot;.

Här följer ett exempel på parametern ExpPartialMatch:

[!DNL ExpPartialMatch off]

Var mycket försiktig när du ställer in den här parametern på&quot;on&quot; eftersom det kan leda till oavsiktlig ommappning av hela webbplatsen.
