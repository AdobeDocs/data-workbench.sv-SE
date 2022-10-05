---
description: Sträng- och numeriska parametrar fungerar som strängar och tal.
title: Sträng- och numeriska parametrar
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# Sträng- och numeriska parametrar{#string-and-numeric-parameters}

{{eol}}

Sträng- och numeriska parametrar fungerar som strängar och tal.

Du kan använda dem omväxlande, men numeriska parametrar måste definieras så att de har ett numeriskt värde. Du kan referera till strängar och numeriska parametrar när du definierar omformningar, villkor och utökade dimensioner, och du kan referera till mer än en parameter på samma rad.

Du kan inte referera till strängar och numeriska parametrar i [!DNL Input] eller [!DNL Output] -fält, men du kan använda en strängparameter för att definiera ett konstant indatafält. Dessutom kan du inte referera till strängar och numeriska parametrar i avkodare eller avkodargrupper.

I det här exemplet visas en [!DNL Log Processing Dataset Include] -fil som definierar en strängparameter och en numerisk parameter. Observera att strängparametern med namnet&quot;Värdeuppslag&quot; definierar en filplats (Lookups\Values) i förhållande till serverinstallationskatalogen för data workbench.

![](assets/cfg_Parameters_StringNumeric.png)
