---
description: Syntaxregler för formler.
title: Syntax för alla uttryck
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 4%

---

# Syntax för alla uttryck{#syntax-for-any-expression}

{{eol}}

Syntaxregler för formler.

* Nyckelorden är skiftlägeskänsliga och måste skrivas exakt som de visas i en formel.
* I en formel måste namn på mått, dimensioner och filter som innehåller mellanslag använda understreck mellan ord. Exempel: [!DNL Page_Views]
* För strängar i uttryck måste du undvika vissa enkla citattecken, dubbla citattecken och omvända snedstreck. Exempel:

   * [!DNL “can’t”] är acceptabelt och behöver inte rymmas, men [!DNL ‘can’t’] är oacceptabelt och måste flyta som [!DNL ‘can\’t’].

   * [!DNL c:\windows] måste escape-konverteras [!DNL c:\\windows].
