---
description: Konceptuell information om delmängder.
title: Förstå delmängder
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---

# Förstå delmängder{#understanding-subsets}

Konceptuell information om delmängder.

Tänk på följande när du använder en delmängd:

* Alla dina prestandatester relaterar nu till din delmängd, inte till hela datauppsättningen, vilket är mycket mer användbart när du analyserar en viss delmängd. Se [Förstå riktmärken](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* Om du använder en delmängd påverkas alla arbetsytor eftersom delmängden används globalt på Datan Workbench.
* Delmängder påverkar bara mått och denorala dimensioner, inte normala dimensioner.
* När du använder [!DNL Report] påverkar delmängder inte data i rapporter som publicerats för andra att visa.
* När du har tillämpat din delmängd används den för allt efterföljande arbete i profilen, inklusive nästa gång du öppnar den här instansen av Data Workbench, tills du tar bort den.
* Den enda plats som anger att en delmängd har använts är den snabbmeny som du når genom att högerklicka på en arbetsyta.

   ![](assets/mnu_Subset.png)

* Du måste arbeta online för att kunna ändra eller ta bort en delmängd. Om du arbetar offline och har använt en delmängd kan du inte visa resultat från hela datauppsättningen. Se [Arbeta offline och online](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >Storleken på delmängden är begränsad till mängden data i filtret som finns på en Data Workbench. Om datauppsättningen sträcker sig över ett serverkluster kommer data för Datan Workbench endast från en Data Workbench i klustret.

En användare hos en stor återförsäljare vill skapa en delmängd (lokal cache) av en viss arbetsvecka med data och sedan köra frågor endast den veckan med data. För att göra detta skapar användaren en delmängd för de aktuella dagarna.

I följande exempel visas ett stolpdiagram över besökare över tiden och en trafikmetrisk teckenförklaring. Den första bilden innehåller inga markeringar: alla data i datauppsättningen representeras. I den andra bilden visas data för en delmängd av Days = {..} av besökare, där Days baseras på ett urval av elementen 1 april till 5 april i Dag-dimensionen.

![](assets/client-sub1.png)
