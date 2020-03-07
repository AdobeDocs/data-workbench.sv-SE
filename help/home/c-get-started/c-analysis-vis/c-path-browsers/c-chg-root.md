---
description: Du kan ändra roten för en sökvägsläsare genom att antingen ange ett element som visas som rot eller lägga till ett nytt element till visualiseringen.
solution: Analytics
title: Ändra roten för sökvägsläsaren
topic: Data workbench
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändra roten för sökvägsläsaren{#change-the-path-browser-s-root}

Du kan ändra roten för en sökvägsläsare genom att antingen ange ett element som visas som rot eller lägga till ett nytt element till visualiseringen.

>[!NOTE]
>
>Du kan inte ange en start- eller slutnod som rot för en sökvägsläsare.

**Ange roten för en sökvägsläsare**

* Högerklicka på önskat element och klicka **[!UICONTROL Set as root]**.

**Lägga till ett nytt element i sökvägsläsaren**

1. Öppna ett diagram eller en tabell som visar måttet vars element du vill visa i sökvägsläsaren.

   Om du till exempel arbetar med webbplatsdata öppnar du ett siddiagram eller en tabell och identifierar den sida som du vill ange som rot.

1. Tryck på Ctrl+Alt och dra det önskade elementet till rotpositionen i sökvägsläsaren.

   >[!NOTE]
   >
   >Du kan ändra den basdimension som är kopplad till en sökvägsläsare genom att dra ett element i den önskade dimensionen till sökvägsläsaren. Det här elementet blir den nya roten i sökvägsläsaren, och etiketten i det övre vänstra hörnet i sökvägsläsaren ändras så att den återspeglar dimensionerna för det här elementet.

   Anta till exempel att du skapar en sidsökvägswebbläsare som visar sidsekvensen för varje session. Om du drar ett element i söktermdimensionen till sökvägsläsaren blir söktermelementet den nya roten och etiketten visar nu sekvensen av söktermer för varje session.

   >[!NOTE]
   >
   >Om du drar ett element till en sökvägsläsare kan det ändra grunddimensionen som är kopplad till sökvägsläsaren, men det påverkar inte nivådimensionen, gruppdimensionen eller måttet. Därför måste du vara försiktig när du väljer en basdimension som är bra när du använder den tillsammans med webbläsarens nivådimension, gruppdimension och mätvärden. Om du vill ändra nivådimension, gruppdimension eller mätvärde måste du redigera sökvägsläsarens [!DNL *.vw] fil i en textredigerare som Anteckningar. Se [Konfigurera sökvägsläsare](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

