---
description: Det nya besökarvillkoret är en villkorsåtgärd som används med webbplatsdata för att avgöra vilka besökare som ska tas med i datauppsättningen.
solution: Analytics
title: Nytt besökarvillkor
topic: Data workbench
uuid: e9733109-5bf3-47ce-974c-d68264291f19
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nytt besökarvillkor{#new-visitor-condition}

Det nya besökarvillkoret är en villkorsåtgärd som används med webbplatsdata för att avgöra vilka besökare som ska tas med i datauppsättningen.

I [!DNL New Visitor Condition] definieras den första loggposten (sorterad efter tid) för en besökare som ska användas i datauppsättningen, och alla efterföljande loggposter för den här besökaren inkluderas i datauppsättningen oavsett om de uppfyller det här villkoret eller inte. Eftersom data [!DNL New Visitor Condition] måste beställas av besökare och tid, tillämpas de bara under datauppsättningens omformningsfas.

I det här exemplet [!DNL New Visitor Condition] skapas en datauppsättning som endast innehåller loggposterna för besökare som svarar på e-postkampanjer. Detta uppnås genom att använda [!DNL NotEmptyCondition] testet (se [Inte tom](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) och [!DNL x-campaign-email] fältet som indata till det reguljära uttrycket. När de nya besökarna som uppfyller villkoret har identifierats, hämtas alla loggposter för dessa besökare.

![](assets/cfg_Transformation_NewVisitorCondition.png)

