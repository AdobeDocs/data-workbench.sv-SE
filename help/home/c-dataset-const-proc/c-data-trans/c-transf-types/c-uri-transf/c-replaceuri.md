---
description: Omvandlingen ReplaceURI ändrar värdet i den interna URI-dimensionen till ett nytt värde.
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 2%

---

# ReplaceURI{#replaceuri}

Omvandlingen ReplaceURI ändrar värdet i den interna URI-dimensionen till ett nytt värde.

Om [!DNL URI Prefix] anges är resultatvärdet helt enkelt URI-prefixet som är sammanfogat med det angivna indatavärdet.

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Standard | Standardvärdet som ska användas om villkoret är uppfyllt och indatavärdet inte är tillgängligt. |  |
| Indata | Värdet som ska ersätta URI:n. |  |
| URI-prefix | Värdet (sträng) som ska föregås av värdet i fältet [!DNL Input]. |  |

>[!NOTE]
>
>Innan du använder [!DNL ReplaceURI]-omformningar bör du skapa en ny enkel dimension med en överordnad [!DNL Page View]från en kopia av cs-uri-system eller cs-uri. Kontakta Adobe om du behöver hjälp med detta.

I det här exemplet visas hur du använder [!DNL ReplaceURI] för att ersätta frågesträngarna &quot;page=*pageid*&quot; med &quot; [!DNL homepage.html]&quot; när *pageid* anger att webbplatsens hemsida visades. Slutresultatet är en användarvänlig vy av URI:n.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

För omvandlingen visas sidan

* [!DNL www.examplesite.com/info.html?page=1550]

ändras till

* [!DNL www.examplesite.com/homepage.html]
