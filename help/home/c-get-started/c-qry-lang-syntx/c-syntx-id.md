---
description: Metrisk, dimension och filteruttryck kan använda identifierare för att referera till namngivna mått, dimensioner och filter.
title: Syntax för identifierare
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Syntax för identifierare{#syntax-for-identifiers}

{{eol}}

Metrisk, dimension och filteruttryck kan använda identifierare för att referera till namngivna mått, dimensioner och filter.

Dessa identifierare är skiftlägeskänsliga och måste anges exakt som de definieras.

En giltig identifierare kan innehålla ett eller flera av följande:

* Understreck (_). Understreck i en identifierare representerar blanksteg i måttet, dimensionen eller filternamnet. Dimensionen Sessionsrefereraren kallas till exempel [!DNL Session_Referrer] i ett uttryck.
* Procenttecken (%)
* Versaler (A-Z)
* Gemener (a-z)
* Dollar-tecken ($)
* Tal (0-9), utom som det första tecknet i en identifierare.
* Icke-ASCII-tecken

Alla andra tecken är ogiltiga i en identifierare.

Samma regler gäller för namn på mått, dimensioner och filter när de används utanför uttryck, förutom att namnen kan innehålla mellanslag men inte understreck. Du kan till exempel definiera dimensionen Sessionsreferens i [!DNL Transformation.cfg] fil som sessionsreferent, men inte [!DNL Session_Referrer].
