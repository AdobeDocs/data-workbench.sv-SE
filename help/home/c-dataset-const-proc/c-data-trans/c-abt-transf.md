---
description: Med omvandlingar kan du extrahera information som finns i dina datafiler och ändra den till en mer användbar form.
solution: Analytics
title: Om omformningar
topic: Data workbench
uuid: 9366f607-741d-4512-9e1b-4165f4291246
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Om omformningar{#about-transformations}

Med omvandlingar kan du extrahera information som finns i dina datafiler och ändra den till en mer användbar form.

Omvandlingar utförs på loggposterna (du kan tänka dig loggposter som datarader) i loggkällorna. För varje datarad får omformningen det angivna indatafältets värde, utför en uppsättning bearbetningssteg och registrerar resultatet i det utdatafält som du anger. Du kan definiera omformningar som ska utföras under antingen loggbearbetnings- eller omformningsfasen i datauppsättningens konstruktionsprocess:

* **Vid loggbearbetning:** Omvandlingar som utförs under loggbearbetningsfasen av datauppsättningens konstruktion tillämpas på varje händelsedatapost (loggpost) för att uppdatera befintliga loggfält eller skapa nya fält. Resultatet av omvandlingarna används tillsammans med villkoren för loggposten för att utvärdera vilka loggposter som filtreras bort från datauppsättningen under loggbearbetningen.
* **Under omformning:** Omvandlingar som utförs under omformningsfasen av datauppsättningens konstruktion utförs på fält med data som skickas från loggbearbetningen för att skapa utökade dimensioner som du kan använda i dina analyser. Se [Utökade dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>Dataindata till omvandling från loggbearbetning ordnas efter tid och grupperas med spårnings-ID:t i källdata. Flera omformningar kräver att data finns i det här formuläret och fungerar bara när de definieras i under omformningen.

Omformningar måste göras med försiktighet. Omvandlingar påverkar inte vilka loggposter som flödar in i datauppsättningsprocessen, men de påverkar själva resultatet. Detta gör det möjligt att ändra det som analyseras utan att ändra de data som analysen bygger på. Omformningsändringar kan dock ändra värdena som skapas i analyser på ett genomgripande sätt.