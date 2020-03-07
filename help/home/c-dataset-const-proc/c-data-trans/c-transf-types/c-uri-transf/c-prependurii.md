---
description: På samma sätt som AppendURI-omformningen påverkar PrependURI-omformningen det interna fält som används av data workbench-servern för att skapa URI-dimensionen.
solution: Analytics
title: PrependURI
topic: Data workbench
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# PrependURI{#prependuri}

På samma sätt som AppendURI-omformningen påverkar PrependURI-omformningen det interna fält som används av data workbench-servern för att skapa URI-dimensionen.

Omvandlingen fungerar genom att lägga till värdet i det identifierade indatafältet framför det värde som för närvarande finns i URI:n. [!DNL PrependURI]

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
