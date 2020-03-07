---
description: Med ett modellvisningsprogram kan du generera en logistisk regressionsmodell med funktionen Propensitetsbedömning.
solution: Analytics
title: Model Viewer
topic: Data workbench
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Model Viewer{#model-viewer}

Med ett modellvisningsprogram kan du generera en logistisk regressionsmodell med funktionen Propensitetsbedömning.

I Model Viewer visas koefficientvikterna för varje indatavariabel (inklusive den konstanta termen) och deras statistiska felintervall. Indatavariabler som visar en hög absolut koefficient och en liten felmarginal är de viktigaste prediktorerna i modellen.

**Så här öppnar du ett Model Viewer-diagram**

1. Välj [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Hovra över modellen Slutförd för en sparad poäng.

![](assets/propensity_model_viewer.png)

Indatavariablerna med koefficienten >= 1 har positiva effekter på benägenhetsmodellen. Koefficienterna som är &lt; 1 är negativa effekter på benägenhetsmodellen. Intervallet som definieras inom parenteserna är felet och anger indatavariabelns konsekvens i den lyckade populationen.
