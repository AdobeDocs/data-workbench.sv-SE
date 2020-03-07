---
description: I matematik är haversine-formeln en ekvation som ger cirkelavstånd mellan två punkter på en sfär som identifieras utifrån deras longituder och latituder.
solution: Analytics
title: Haversine
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Haversine{#haversine}

I matematik är haversine-formeln en ekvation som ger cirkelavstånd mellan två punkter på en sfär som identifieras utifrån deras longituder och latituder.

Precis som för formeln kräver [!DNL Haversine] omformningen två uppsättningar [!DNL Latitude] - och [!DNL Longitude] -inställningar, och använder dessa fyra indata för att beräkna det verkliga avståndet mellan två platser på jorden.

Avståndet kan representeras som engelska mil eller kilometer genom att flaggan&quot;In Kilometers&quot; ändras från false till true.

![](assets/cfg_TransformationType_Haversine.png)

| Parameter | Beskrivning | Standard |
|---|---|---|
| Namn | Beskrivande namn på omformningen. Här kan du ange valfritt namn. |  |
| Kommentarer | Valfritt. Anteckningar om omvandlingen. |  |
| Villkor | De villkor som den här omformningen används under. |  |
| Latitude 1-fält | Latitud för punkt 1. |  |
| Latitude 2-fält | Latitud för punkt 2. |  |
| Longitud 1-fält | Longitud för punkt 1. |  |
| Longitud 2-fält | Longitud för punkt 2. |  |
| Utdata | När det är beräknat innehåller fältet [!DNL Output] avstånd mellan de punkter som är avsedda som element i en dimension. |  |

Om du till exempel kodar Lat1, Lon1 i en latitud och longitud på deras butik och använder en IP-lookup lat och lång för sina kunder, kan avståndet till en butik som de flesta kunder köper från eller kommer från avgöras.

>[!NOTE]
>
>Om du vill identifiera avstånd för andra platser, måste varje enskild plats ha en egen uppsättning med sista- och längdfält.
