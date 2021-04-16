---
description: En visualisering av guidad analys ger tips för ytterligare analys baserat på de val du gör på en arbetsyta.
title: Guidad analys
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Guidad analys{#guided-analysis}

En visualisering av guidad analys ger tips för ytterligare analys baserat på de val du gör på en arbetsyta.

Den här visualiseringen hjälper dig att identifiera vilka dimensioner som kan ge dig mer information, det vill säga de som är mest korrelerade med dina val. I visualiseringen av den guidade analysen i ditt Adobe-program visas de dimensioner som är relevanta för din datauppsättning, som i följande guidade analys [!DNL Site]-visualisering.

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>Om ett dimensionsnamn visas i rött definieras det inte i datauppsättningen.

När du gör en markering i en arbetsyta visar visualiseringen av guidad analys bockmarkeringar till vänster och punkter till höger om dimensionerna för att visa vilken som ger den mest relevanta informationen:

* **Kontrollera** markeringen för att identifiera de dimensioner vars värden skiljer sig från referensvärdet på ett statistiskt signifikant sätt (dvs. skillnaden mellan urvalet och referensvärdet beror inte på en slumpmässig risk).
* **Ange** i vilken utsträckning urvalet skiljer sig från referensvärdet. Den första punkten representerar U-statistik och den andra punkten representerar V-statistik. Se [Förstå de statistiska åtgärderna](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). Ju ljusare och större punkter, desto större skillnad och mer relevant information om måttet baserat på din markering (d.v.s. ljusare, större punkter representerar mer användbar information).
