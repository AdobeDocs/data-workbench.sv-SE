---
description: Du kan visualisera data från flera profiler på en och samma kontrollpanel.
title: Korsprofilmarkeringar
uuid: e9377bcf-8de9-4952-a81a-863216f25fb7
exl-id: a14400bf-64e3-44be-b9ab-d8a9ded406ae
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Korsprofilmarkeringar{#cross-profile-selections}

{{eol}}

Du kan visualisera data från flera profiler på en och samma kontrollpanel.

I vissa fall kan även markeringar från en visualisering tillämpas på visualiseringar från en annan profil. Om du till exempel skapar visualiseringar från en **[!UICONTROL Call Center]**profil och **[!UICONTROL Website Traffic]** på en kontrollpanel kan du välja en målmånad om du vill att data i alla visualiseringar ska segmenteras samtidigt den månaden, trots att det är helt olika datauppsättningar.

När det finns visualiseringar från flera profiler på en kontrollpanel kan du göra ett val i en visualisering om den visualiseringens dimension också finns på alla andra profiler som visas på skärmen. Markeringar inaktiveras emellertid om en dimension inte hittas globalt i alla andra visualiseringar på skärmen och användarna ser en **[!UICONTROL Selections Disabled]** meddelande.

![](assets/selection_disabled.png)

>[!NOTE]
>
>Även om dimensioner kan ha samma namn i flera profiler har de kanske inte samma betydelse. Det är viktigt att undersöka varje dimension för att avgöra om det är lämpligt att använda den för att göra markeringar över flera profiler.
