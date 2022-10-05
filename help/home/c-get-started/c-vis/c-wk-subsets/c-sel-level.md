---
description: När du skapar en delmängd måste du ange en nivå.
title: Välj en nivå
uuid: 18c2bee7-a70f-4510-978f-830b56780f47
exl-id: 39d8407c-e2ec-4080-8918-26cafbf988df
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Välj en nivå{#select-a-level}

{{eol}}

När du skapar en delmängd måste du ange en nivå.

En nivå är valfri räkningsbar dimension. Om du till exempel arbetar med webbplatsdata och väljer elementet Tue från dimensionen Day of Week och skapar en delmängd, måste du välja den nivå som du vill visa: Sidvy, session eller besökare.

* **Dag i veckan=&quot;Nyans&quot; per sidvy:** På sidvisningsnivån visas endast de sidvyer som inträffade en tisdag.

   ![](assets/vis_Subset_byPageView.png)

* **Day of Week=&quot;Tue&quot; by Session:** Sessionsnivån visar endast de sessioner som ägde rum på en tisdag.

   ![](assets/vis_Subset_bySession.png)

* **Day of Week=&quot;Tue&quot; av besökaren:** Besökarnivån visar alla besökare som kom till webbplatsen på tisdagar, men den visar även andra dagar att samma besökare kom till webbplatsen.

   ![](assets/vis_Subset_byVisitor.png)
