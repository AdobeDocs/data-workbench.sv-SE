---
description: Metrisk, dimension och filteruttryck kan använda identifierare för att referera till namngivna mått, dimensioner och filter.
solution: Analytics
title: Syntax för identifierare
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax för identifierare{#syntax-for-identifiers}

Metrisk, dimension och filteruttryck kan använda identifierare för att referera till namngivna mått, dimensioner och filter.

Dessa identifierare är skiftlägeskänsliga och måste anges exakt som de definieras.

En giltig identifierare kan innehålla ett eller flera av följande:

* Understreck (_). Understreck i en identifierare representerar blanksteg i måttet, dimensionen eller filternamnet. Dimensionen Sessionsreferens kallas till exempel [!DNL Session_Referrer] i ett uttryck.
* Procenttecken (%)
* Versaler (A-Z)
* Gemener (a-z)
* Dollar-tecken ($)
* Tal (0-9), utom som det första tecknet i en identifierare.
* Icke-ASCII-tecken

Alla andra tecken är ogiltiga i en identifierare.

Samma regler gäller för namn på mått, dimensioner och filter när de används utanför uttryck, förutom att namnen kan innehålla mellanslag men inte understreck. Du kan till exempel definiera dimensionen Sessionsreferens i [!DNL Transformation.cfg] filen som Sessionsreferens, men inte [!DNL Session_Referrer].
