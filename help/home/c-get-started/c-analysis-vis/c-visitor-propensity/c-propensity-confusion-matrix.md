---
description: De statistiska beräkningarna för Propensitetsbedömning är definierade.
solution: Analytics
title: Beräknar benägenhetsbedömning
topic: Data workbench
uuid: 67270864-0468-4cc9-b48b-0e880f813555
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Beräknar benägenhetsbedömning{#calculating-propensity-scoring}

De statistiska beräkningarna för Propensitetsbedömning är definierade.

Poängen som beräknas för varje besökare är en uppskattad sannolikhet att den angivna händelsen (definierad av målfiltret) kan inträffa, vilket resulterar i ett poängvärdesintervall från 0 till 100 procent. Bedömningsprocessen använder befintliga exempel som utbildningsdata för att hitta förhållandet mellan händelsens sannolikhet och de valda oberoende variablerna av intresse.

Sådana relationer återspeglas matematiskt i varje kvantitativt värde som associeras för varje oberoende variabel. Dessa värden kallas för modellkoefficienter. ScoreDim använder för närvarande algoritmen IRLS (Iterally Reweight Least Squares) för att beräkna modellkoefficienterna. IRLS går igenom proverna flera gånger tills skillnaden på koefficienter mellan aktuellt pass och föregående pass är mindre än 1,0e-6, då det kallas **konvergerat**. Beroende på data kan IRLS dock inte uppnå konvergens.

I så fall kommer standardutbildningen att upphöra när

* koefficientskillnaden blir större i stället för mindre,
* 1 000 pass har nåtts, eller
* ett matematiskt fel förhindrar fortsatt iteration.

Om IRLS inte konvergerar används en säkerhetskopieringsalgoritm som kallas för Stochastic Gradient Decent (SGD). SGD kommer också att genomgå utbildningsproven flera gånger. Men till skillnad från IRLS styrs SGD-modellkoefficienterna så att skillnaden mellan upprepningar alltid minskar exponentiellt. På samma sätt kommer SGD att upphöra när koefficientdifferensen underskrider 1,0e-6 eller 100 000 passeringar har uppnåtts. Om IRLS och SGD inte fungerar registreras detta i spårningsloggen.

För båda algoritmerna ingår inte alla exempel i modellutbildning. 80 procent används för att utbilda modellen. När modellen har tränats används de återstående 20 procenten för att bedöma modellstyrkan i form av noggrannhet, återkallelse och precision, som beräknas utifrån den sammansatta matrisen. Ju närmare 100 %, desto bättre blir poängmodellen.
