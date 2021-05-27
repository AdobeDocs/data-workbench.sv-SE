---
description: En Adobe-datauppsättning innehåller de data som har lästs in och bearbetats av data workbench-servern.
title: Om datauppsättningskonstruktion
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
exl-id: 111e98b5-d899-4f79-90ce-70f520d527d6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Om datauppsättningskonstruktion{#understanding-dataset-construction}

En Adobe-datauppsättning innehåller de data som har lästs in och bearbetats av data workbench-servern.

Stegen som ingår i inläsningen och bearbetningen av data av data workbench-servern (InsightServer64.exe) utgör datauppsättningens konstruktionsprocess.

>[!NOTE]
>
>En data workbench-server som bearbetar och skickar data från en datauppsättning från Adobe kallas databehandlingsenhet eller DPU. Den kallas ibland för en bearbetningsserver eller frågeserver. Data workbench och [!DNL Report]-klienter interagerar direkt med DPU:er.

Under datauppsättningen läser data workbench-servern källdata från loggkällor, tillämpar omformningar på specifika datafält och definierar utökade dimensioner som ska skapas från de omformade fälten. Byggprocessen sker i två faser: *Loggbearbetning* och *Transformation*. När datauppsättningen har skapats kan du använda datauppsättningens utökade mått för att skapa härledda mått och dimensioner för dina specifika analyssyften.

Datauppsättningen är som en tillverkningsprocess. Du väljer de data (råmaterialen) som ska användas för att skapa datauppsättningen, och du definierar de dataomvandlingar (processstegen) som ändrar den information som finns tillgänglig i data för att skapa utökade dimensioner (de tillverkade produkterna).

<!--
c_log_proc.xml
-->

Loggarna filtreras och fälten med data som ska skickas till omvandlingsfasen identifieras. I slutet av loggbearbetningsfasen grupperas data efter spårnings-ID (det vill säga alla loggposter med samma spårnings-ID grupperas tillsammans) och sorteras i tid. Under loggbearbetningsfasen kan du inte komma åt de bearbetade data som ska användas för analys.

## Ange loggkällor {#section-75279dd6a7304d469735562796741d0f}

Loggkällor är filer som innehåller de data som ska användas för att skapa en datauppsättning. De data som är tillgängliga i loggkällorna kallas händelsedata eftersom varje datapost representerar en transaktionspost eller en enda instans av en händelse. Dessutom innehåller varje post, eller loggpost, ett värde som kallas spårnings-ID.

>[!NOTE]
>
>När du väljer loggkällor måste du se till att varje loggpost innehåller ett spårnings-ID för entiteten som ska representera den högsta nivån som dina data ska grupperas på. Om du till exempel arbetar med data som samlats in från webbplatstrafiken, är det troligt att du väljer besökare som den här entiteten. Varje besökare har ett unikt spårnings-ID, och alla data om en viss besökare kan grupperas tillsammans. Kontakta Adobe om du behöver hjälp.

En loggkällas händelsedata samlas in i realtid av [!DNL Sensors] eller extraheras från arkiverade datakällor av Insight Server. Händelsedata som samlas in av sensorer från HTTP- och programservrar överförs till Insight-servrar, som konverterar data till mycket komprimerade loggfiler ( [!DNL .vsl]). Händelsedata som finns i en platt fil, XML-fil eller en ODBC-datakälla läses av Insight Server, som innehåller avkodare som du definierar för att extrahera en gemensam uppsättning loggfält från dessa olika format.

## Definiera omformningar {#section-55a8cdb47379484081e53087f074778d}

En omformning är en uppsättning instruktioner som du kan definiera för att extrahera eller ändra information i händelsedata. Varje omformning som du definierar tillämpas på varje händelsedatapost (loggpost) för att uppdatera befintliga loggfält eller skapa nya fält. Resultatet av omvandlingar används tillsammans med villkoren för loggpost för att utvärdera vilka loggposter som filtreras bort från datauppsättningen under loggbearbetningen.

Alla typer av omformningar kan inte användas under datauppsättningens loggbearbetningsfas.

## Filtreringsloggar {#section-6172ca0fb0eb4177925151bb49fdbc02}

Datauppsättningen innehåller flera parametrar som används för att filtrera data som flödar från omformningarna. Filtrering används för att ange vilka loggposter som ska användas i efterföljande bearbetningssteg. Filter kan till exempel definieras av, tidsintervall, status för serverns svar eller IP-adress och användaragentinformation. [!DNL Log Entry Condition] är ett anpassningsbart filtreringstest. Testet letar efter vissa villkor i fälten för varje loggpost för att avgöra om posten ska fortsätta i datauppsättningsprocessen. Om en loggpost inte uppfyller villkoret tas posten bort från konstruktionsprocessen.

## Identifiera fält för omformning {#section-eef98ca723e54547b887aefdf0514c47}

Om ett datafält ska skickas från loggbearbetningsfasen till transformeringsfasen för vidare bearbetning, måste du identifiera det under loggbearbetningen. Detta krav gäller oavsett om fältet är tillgängligt från loggkällorna eller om det har skapats från dataomvandlingar som har använts på data under loggbearbetningen.

<!--
c_transformation.xml
-->

Under datauppsättningens omformningsfas utförs bearbetningen av grupperade och ordnade data som genereras från loggbearbetningen. Ytterligare dataomvandlingar utförs och utökade datamått skapas för användning i analyserna. Under omformningsfasen får du tillgång till ett statistiskt urval av data som blir större när omformningsfasen närmar sig slutförandet.

## Definiera omformningar {#section-001b3fd4c1dd4dd38a5536872bc9de68}

Du kan definiera omformningar som ska användas under omformningsfasen i datauppsättningsprocessen för att underlätta skapandet av de utökade dimensionerna. Varje omformning tillämpas på varje händelsedatapost (loggpost) som skickas från loggbearbetningen.

## Filtreringsloggar {#section-3fed0a00ca344a719b5e8db363f64f06}

[!DNL Log Entry Condition] kan användas under omformningen för att söka efter specifika villkor i fälten för varje loggpost som kommer från loggbearbetningen. Om en loggpost inte uppfyller villkoret tas posten bort från konstruktionsprocessen.

## Definiera utökade Dimensioner {#section-25efafd0bfc84c86b9717d453a88c91b}

Utökade dimensioner är de slutliga produkterna i datauppsättningsprocessen. De representerar relationer mellan loggfälten i data. Använd dem för att skapa visualiseringar, bygga upp utökade mätvärden eller utföra analyser för att förstå åtgärder och problem som är specifika för din verksamhet.
