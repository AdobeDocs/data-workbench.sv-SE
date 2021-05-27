---
description: Du kan ändra roten för en sökvägsläsare genom att antingen ange ett element som visas som rot eller lägga till ett nytt element till visualiseringen.
title: Ändra roten för sökvägsläsaren
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
exl-id: 09842b93-af26-42b9-9395-a02b86978b21
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Ändra sökvägen till webbläsarens rot{#change-the-path-browser-s-root}

Du kan ändra roten för en sökvägsläsare genom att antingen ange ett element som visas som rot eller lägga till ett nytt element till visualiseringen.

>[!NOTE]
>
>Du kan inte ange en start- eller slutnod som rot för en sökvägsläsare.

**Ange roten för en sökvägsläsare**

* Högerklicka på önskat element och klicka på **[!UICONTROL Set as root]**.

**Lägga till ett nytt element i sökvägsläsaren**

1. Öppna ett diagram eller en tabell som visar måttet vars element du vill visa i sökvägsläsaren.

   Om du till exempel arbetar med webbplatsdata öppnar du ett siddiagram eller en tabell och identifierar den sida som du vill ange som rot.

1. Tryck på Ctrl+Alt och dra det önskade elementet till rotpositionen i sökvägsläsaren.

   >[!NOTE]
   >
   >Du kan ändra den basdimension som är kopplad till en sökvägsläsare genom att dra ett element i den önskade dimensionen till sökvägsläsaren. Det här elementet blir den nya roten i sökvägsläsaren, och etiketten i det övre vänstra hörnet i sökvägsläsaren ändras så att den återspeglar dimensionerna för det här elementet.

   Anta till exempel att du skapar en sidsökvägswebbläsare som visar sidsekvensen för varje session. Om du drar ett element i söktermdimensionen till sökvägsläsaren blir söktermselementet den nya roten och etiketten visar nu sekvensen av söktermer för varje session.

   >[!NOTE]
   >
   >Om du drar ett element till en sökvägsläsare kan det ändra grunddimensionen som är kopplad till sökvägsläsaren, men det påverkar inte nivådimensionen, gruppdimensionen eller måttet. Därför måste du vara försiktig när du väljer en basdimension som är bra när du använder den tillsammans med webbläsarens nivådimension, gruppdimension och mätvärden. Om du vill ändra nivådimensionen, gruppdimensionen eller måttet måste du redigera sökvägen till webbläsarens [!DNL *.vw]-fil i en textredigerare som Anteckningar. Se [Konfigurera sökvägsläsare](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
