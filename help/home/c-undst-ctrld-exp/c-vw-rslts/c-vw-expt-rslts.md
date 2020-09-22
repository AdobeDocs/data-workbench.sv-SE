---
description: När du har lagt till det nya fältet i Log Processing.cfg och skapat den nya delade omvandlingen och den utökade dimensionen, kan du visa den nya utökade dimensionen som du skapade så fort som den snabba inmatningsfasen av databearbetningen har slutförts.
solution: Analytics,Analytics
title: Visa experimentresultat
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---


# Visa experimentresultat{#viewing-the-experiment-results}

När du har lagt till det nya fältet i Log Processing.cfg och skapat den nya delade omvandlingen och den utökade dimensionen, kan du visa den nya utökade dimensionen som du skapade så fort som den snabba inmatningsfasen av databearbetningen har slutförts.

Den här dimensionen visar som standard antalet sessioner för varje experimentgrupp.

**Visa experimentdimensionen**

* I valfri arbetsyta i [!DNL Insight]öppnar du en tabell med den experimentella dimension du har skapat.

   Experimentdimensionselementen, som representerar varje experiment som du för närvarande kör och varje grupp inom varje experiment, visas med det aktuella antalet sessioner för varje grupp. Varje grupp namnges i följande format med experimentnamnet följt av gruppnamnet:

   *Experimentnamn.gruppnamn*

   Exempel: [!DNL New Homepage.Control]

I följande tabell visas dimensionen Kontrollerade experimentgrupper som skapades i [!DNL Transformation.cfg] och alla experiment och deras grupper.

Experimentet New Homepage visas längst ned i tabellen med de två grupperna: Kontroll och index2.

![](assets/controlledexpgrps.png)

Nu kan ni använda experimentella dimensioner och relevanta mätvärden för att utforska och tolka experimentresultaten samt skapa användbara rapporter som detaljerar dessa resultat.
