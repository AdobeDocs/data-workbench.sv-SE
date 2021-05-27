---
description: På samma sätt som AppendURI-omformningen påverkar PrependURI-omformningen det interna fält som används av data workbench-servern för att skapa URI-dimensionen.
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 2%

---

# PrependURI{#prependuri}

På samma sätt som AppendURI-omformningen påverkar PrependURI-omformningen det interna fält som används av data workbench-servern för att skapa URI-dimensionen.

[!DNL PrependURI]-omformningen fungerar genom att lägga till värdet i det identifierade indatafältet framför det aktuella värdet i URI:n.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Standardvärdet som ska användas om villkoret är uppfyllt och indatavärdet inte är tillgängligt. |  |
| Indata | Namnet på det fält vars värde är prepended för URI:n. |  |

Följande exempel lägger bara in s-dns-fältet i URI:n, vilket utökar representationen av URI-dimensionen så att den domän som begärts av klientenheten inkluderas.

![](assets/cfg_TransformationType_PrependURI.png)

I det här exemplet väntar s-dns-fältet på URI:n

* [!DNL /modelview.asp&id=login]

resulterar i följande URL:

* [!DNL www.adobe.com/modelview.asp?id=login]

Nu utökas URI:n så att den begärda domänen inkluderas.
