---
description: Du kan skapa en sökvägsläsare från ett diagram, en tabell eller ett processdiagram.
title: Skapa sökvägsläsare
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
exl-id: 9fa11b84-da73-447a-8b10-7eab381e3f66
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---

# Skapa sökvägsläsare{#creating-path-browsers}

Du kan skapa en sökvägsläsare från ett diagram, en tabell eller ett processdiagram.

**Skapa en banwebbläsare från ett diagram eller en tabell**

1. Lägg till en sökvägsläsare på arbetsytan. Visualiseringen är tom förutom etiketten (sekvens av..) i det övre vänstra hörnet.
1. Öppna ett diagram eller en tabell som visar måttet vars element du vill visa i sökvägsläsaren. Om du till exempel arbetar med webbplatsdata öppnar du ett siddiagram eller en tabell och identifierar den sida som du vill ange som rot.
1. Tryck på Ctrl+Alt och dra det önskade elementet till sökvägsläsaren. Etiketten i det övre vänstra hörnet av sökvägsläsaren ändras så att den motsvarar den grunddimension vars element du drar till sökvägsläsaren.

>[!NOTE]
>
>Om du drar ett element till en sökvägsläsare kan det ändra grunddimensionen som är kopplad till sökvägsläsaren, men det påverkar inte nivådimensionen, gruppdimensionen eller måttet. Därför måste du vara försiktig när du väljer en basdimension som är bra när du använder den tillsammans med webbläsarens nivådimension, gruppdimension och mätvärden. Om du vill ändra nivådimensionen, gruppdimensionen eller måttet måste du redigera sökvägen till webbläsarens [!DNL *.vw]-fil i en textredigerare som Anteckningar. Se [Konfigurera sökvägsläsare](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**Skapa en sökvägsläsare från en processkarta**

>[!NOTE]
>
>En sökvägsläsare som skapats från en processkarta visar endast de element som visas på processkartan. Andra element i basdimensionen visas inte.

1. Skapa en processkarta. Se [Skapa processkartor](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. Dra det önskade elementet från processkartan till banwebbläsaren. Elementet blir roten i sökvägsläsaren.

>[!NOTE]
>
>När du skapar en sökvägsläsare från en processkarta, ignorerar sökvägsläsaren elementen i nivådimensionen utan tillhörande basdimensionselement. När du drar en nod från en processkarta till en sökvägsläsare definieras banwebbläsarens basdimension (med namnet Karta) av processkartan och dess element begränsas till elementen på processkartan. Därför har vissa element i sökvägsläsarens nivådimension inte associerade basdimensionselement och visas inte i sökvägsläsaren.
