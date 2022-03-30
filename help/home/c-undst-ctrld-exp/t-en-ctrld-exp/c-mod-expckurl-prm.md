---
description: Parametern ExpCookieURL kan användas för att testa att ditt kontrollerade experiment fungerar som det ska.
solution: Analytics
title: Ändra parametern ExpCookieURL (valfritt)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Ändra parametern ExpCookieURL (valfritt){#modifying-the-expcookieurl-paramter-optional}

Parametern ExpCookieURL kan användas för att testa att ditt kontrollerade experiment fungerar som det ska.

Den här parametern definierar URL:en för en virtuell sida som när den efterfrågas placerar dig i ett visst experiment och en viss grupp och sedan dirigerar om dig till webbplatsens rot. Från den punkten till slutet av experimentet ingår du i det angivna experimentet och gruppen.

Standardsidan för den här parametern är [!DNL setcookie.htm], men du kan använda vilken giltig virtuell URL som helst.

>[!NOTE]
>
>Detta måste vara en virtuell URL och får inte vara en riktig sida eller en del av befintligt innehåll. Det ska inte finnas någon fil på webbservern på den angivna sökvägen med det angivna namnet.

Här följer ett exempel på parametern ExpCookieURL:

[!DNL ExpCookieURL /setcookie.htm]
