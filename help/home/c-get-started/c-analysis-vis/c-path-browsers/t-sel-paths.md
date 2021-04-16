---
description: Du kan markera en bana i en sökvägsläsare för att skapa filter som innehåller data som är kopplade till elementen i sökvägen.
title: Markera en bana
uuid: 3131df2f-674f-44b8-9006-d8cb1ecf3874
exl-id: c560dfd0-ccaf-4a60-88a1-29a33f8aa014
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Välj en sökväg{#select-a-path}

Du kan markera en bana i en sökvägsläsare för att skapa filter som innehåller data som är kopplade till elementen i sökvägen.

När du väljer en sökväg med basdimensionselement i en sökvägsläsare, markerar du data för motsvarande element i nivådimensionen.

Anta till exempel att du har skapat en sökvägsläsare som visar sidor på en webbplats. Varje sida är ett element i siddimensionen och sidans nivådimension är Sidvy. När du markerar en sökväg med sidor i en sökvägsläsare, väljer du data för de sidvyer som är kopplade till de sidorna.

>[!NOTE]
>
>Du kan ändra standardnivådimensionen för en sökvägsläsare. Instruktioner om hur du konfigurerar en sökvägsläsare finns i [Konfigurera sökvägsläsare](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

1. Klicka på ett element i sökvägsläsaren för att utöka den visade sökvägen till vänster eller höger om roten.
1. Högerklicka på önskat element och klicka på **[!UICONTROL Select path]**. Den markerade banan kontureras med vitt.

   >[!NOTE]
   >
   >Du kan inte välja en start- eller slutnod.

1. Upprepa steg 1 för varje element som du vill lägga till i banan.

   Om du till exempel arbetar med webbplatsdata kan du välja en sökväg för sidorna på webbplatsen.

   ![](assets/client-path.png)

   Den här sökvägen utgör en markering och alla andra öppna visualiseringar på arbetsytan (inklusive förklaringar) uppdateras för att visa data som är kopplade till den bana som skapas av de markerade elementen. Se [Göra markeringar i visualiseringar](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).
