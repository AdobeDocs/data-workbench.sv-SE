---
description: Efter installationen fungerar det digitala certifikatet som utfärdas av Adobe som en nyckel som gör att du kan köra Report Server.
title: Återvalidera det digitala certifikatet (översikt)
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Validera det digitala certifikatet igen{#re-validating-the-digital-certificate}

Efter installationen fungerar det digitala certifikatet som utfärdas av Adobe som en nyckel som gör att du kan köra Report Server.

**Rekommenderad frekvens:** Vid behov

Ett digitalt certifikat måste vara aktuellt för att fungera korrekt.

För att ditt digitala certifikat ska förbli aktuellt måste det valideras regelbundet (vanligtvis var 30:e dag, men detta kan variera beroende på ditt avtal med Adobe). Om datorn har Internet-åtkomst är valideringsprocessen helt genomskinlig. [!DNL Report Server] ansluter automatiskt till Adobe License Server och validerar certifikatet vid behov på nytt. Om datorn inte har Internetåtkomst måste du hämta ett nytt, verifierat certifikat från Adobe License Server och installera det på datorn enligt stegen i [Hämta och installera det digitala certifikatet](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
