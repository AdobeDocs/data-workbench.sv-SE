---
description: Med AppendURI-omvandlingen kan du lägga till information till standardvärdet som kommer från loggposterna som används för att skapa datauppsättningen.
solution: Analytics
title: AppendURI
topic: Data workbench
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# AppendURI{#appenduri}

Med AppendURI-omvandlingen kan du lägga till information till standardvärdet som kommer från loggposterna som används för att skapa datauppsättningen.

Omvandlingen placerar ett namn/värde-par i slutet av det interna fält som används för att skapa URI-dimensionen. Paret name-value skapas med parametern Query String Key som namn och värde för den identifierade indataparametern som värde för paret. Kommandot lägger [!DNL AppendURI] till lämpliga kommandon - och &amp; symboler som krävs för att separera namnvärdespar från [!DNL URI] stammen och från tidigare [!DNL AppendURI] åtgärder som kan ha tillämpats på URI:n.

Omformningen fungerar bara när den [!DNL AppendURI] definieras i [!DNL Transformation.cfg] filen eller en [!DNL Transformation Dataset Include] fil.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Standardvärdet som ska användas om villkoret är uppfyllt och indatavärdet inte är tillgängligt. |  |
| Indata | Namnet på det fält vars värde läggs till i URI:n. |  |
| Frågesträngsnyckel | Namnet som ska användas när namnvärdespar skapas. |  |

Tänk dig en webbplats som har skapats med en traditionell modell-View-Controller-metod. I sådana system är det vanligt att ha en enda webbsida som är den punkt där man får åtkomst till systemet. För en sådan webbplats skulle en visualisering av trafikmönster i systemet vara mycket ointressant och skulle inte ge några insikter om besökaranvändning och trafikflöde. Ta till exempel en webbplats som samlar alla webbförfrågningar via en URI i följande format:

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

ASP-sidan för modellvyn tar emot all trafik och fastställer dess åtgärder baserat på värdet för ID-fältet i frågan. Som standard innehåller URI-dimensionen en enda post:

* [!DNL modelview.asp]

Detta skulle leda till en ganska ointressant mappning av trafiken genom webbplatsen, eftersom all trafik dirigeras via en enda URI. För att åtgärda det här scenariot och ge en mer informativ bild av webbplatsens underliggande arkitektur kan du [!DNL AppendURI] använda för att flytta några av de unika namnvärdesparen från cs-uri-query-fältet till den URI-dimension som används för visualiseringar. Omformningen som visas nedan ger information om en sådan omformning:

![](assets/cfg_TransformationType_AppendURI.png)

I det här exemplet används två sidor av systemet för att hantera alla begäranden: [!DNL modelview.asp] och [!DNL xmlmodelview.asp]. Den ena sidan används för webbläsartrafik och den andra används för XML-kommunikation system-till-system. Programserverprocessen använder ID-namnet för cs-uri-query för att avgöra vilken åtgärd som ska utföras. Därför kan du extrahera värdet från id-fältet och lägga till det i URI:n. Resultatet är en samling URI:er med en variationsbredd som återspeglar besökstrafiken via webbplatsen. Här anger ett [!DNL String Match] villkor vilka loggposter som omformningen ska tillämpas på genom att söka i fältet cs-uri-stam efter de två webbsidor som är av intresse och ignorera alla andra. Indata (värdet för vårt namnvärdespar) är resultatet av cs-uri-query(id), som är &quot;login&quot;. Enligt parametern Query String Key är namnet som läggs till&quot;id&quot;. För det inkommande cs-uri-värdet i vårt exempel är därför den resulterande URI som används av [!DNL URI] dimensionen [!DNL /modelview.asp&id=login].
