---
description: När du har driftsatt ditt experiment bör du verifiera att experimentet fungerar som det ska.
solution: Analytics
title: Validera experimentversionen
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---

# Validera experimentversionen{#validating-the-experiment}

När du har driftsatt ditt experiment bör du verifiera att experimentet fungerar som det ska.

Som beskrivs i [Ändra parametern ExpCookieURL (valfritt)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf), sidan som anges i parametern ExpCookieURL i [!DNL Sensor] konfigurationsfilen kan användas för att placera dig själv i en specifik experimentgrupp.

Den virtuella standardsidan är [!DNL /setcookie.htm], men du måste använda det värde som du anger i parametern ExpCookieURL.

## Begär testsidan {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Om du vill testa en specifik experimentgrupp för webbplatsen måste webbläsaren vara konfigurerad att acceptera cookies och du får inte redan ha en cookie för den här webbplatsen.

Varje gång du vill testa en ny grupp måste du rensa dina cookies för webbplatsen.

Om du vill placera dig själv i en viss grupp inom ett specifikt experiment begär du testsidan med en frågesträng i följande format:

[!DNL https://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

Exempel:

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

När den virtuella URL-begäran skickas till servern, [!DNL Sensor] identifierar dig som medlem i den angivna gruppen i det angivna experimentet och dirigerar sedan om dig till webbplatsens rot. Nu kan du navigera till rätt plats på webbplatsen för att kontrollera om rätt innehåll visas för det experimentet och gruppen.

Om du skrev in följande i webbläsaren skulle webbläsaren visa webbplatsens hemsida och placera dig i gruppen index2 i New_Homepage-experimentet:

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

När besökare i index2-gruppen begär hemsidan visas den grafiska länken &quot;Begär en demo&quot; högre upp på sidan, som i följande bild:

![](assets/TestPage.png)
