---
description: Sträng- och numeriska parametrar fungerar som strängar och tal.
solution: Analytics
title: Sträng- och numeriska parametrar
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sträng- och numeriska parametrar{#string-and-numeric-parameters}

Sträng- och numeriska parametrar fungerar som strängar och tal.

Du kan använda dem omväxlande, men numeriska parametrar måste definieras så att de har ett numeriskt värde. Du kan referera till strängar och numeriska parametrar när du definierar omformningar, villkor och utökade dimensioner, och du kan referera till mer än en parameter på samma rad.

Du kan inte referera till strängar och numeriska parametrar i [!DNL Input] - eller [!DNL Output] -fält, men du kan använda en strängparameter för att definiera ett konstant indatafält. Dessutom kan du inte referera till strängar och numeriska parametrar i avkodare eller avkodargrupper.

I det här exemplet visas en [!DNL Log Processing Dataset Include] fil som definierar en strängparameter och en numerisk parameter. Observera att strängparametern med namnet&quot;Värdeuppslag&quot; definierar en filplats (Lookups\Values) i förhållande till serverinstallationskatalogen för data workbench.

![](assets/cfg_Parameters_StringNumeric.png)

