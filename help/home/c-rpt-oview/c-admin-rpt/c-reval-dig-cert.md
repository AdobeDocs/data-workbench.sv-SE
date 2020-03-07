---
description: Efter installationen fungerar det digitala certifikatet som utfärdas av Adobe som en nyckel som gör att du kan köra Report Server.
solution: Analytics
title: Validera det digitala certifikatet igen
topic: Data workbench
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Validera det digitala certifikatet igen{#re-validating-the-digital-certificate}

Efter installationen fungerar det digitala certifikatet som utfärdas av Adobe som en nyckel som gör att du kan köra Report Server.

**Rekommenderad frekvens:** Vid behov

Ett digitalt certifikat måste vara aktuellt för att fungera korrekt.

För att ditt digitala certifikat ska förbli aktuellt måste det valideras regelbundet (vanligtvis var 30:e dag, men detta kan variera beroende på ditt avtal med Adobe). Om datorn har Internet-åtkomst är valideringsprocessen helt genomskinlig. [!DNL Report Server] ansluter automatiskt till Adobe License Server och omvaliderar certifikatet vid behov. Om din dator inte har Internet-åtkomst måste du hämta ett nytt, verifierat certifikat från Adobe License Server och installera det på din dator enligt stegen i [Hämta och installera det digitala certifikatet](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
