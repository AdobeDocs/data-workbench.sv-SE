---
description: Nedan följer krav och rekommendationer för hur du installerar arbetsstationen (klienten) i Datan Workbench.
title: Krav på arbetsstation
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Krav på arbetsstation{#workstation-requirements}

Nedan följer krav och rekommendationer för hur du installerar arbetsstationen (klienten) i Datan Workbench.

Mer information om systemkrav för Data Workbench finns i [Systemkrav för serversystem](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html).

>[!IMPORTANT]
>
>Server-, rapportserver- och klientkomponenterna uppgraderas för att köras på 64-bitars Windows-operativsystem.

**Innan du börjar**

Kontrollera att du har utfört de här åtgärderna innan du installerar Data Workbench Workstation (Client):

* **** ***AddExcluded-*** processer för  *MS System Center Endpoint Protection i Windows 2012-* servrar för följande körbara filer:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Detta aktiverar tillåtelselista-rättigheter för dessa korsande körbara filer.

* **Installera Microsoft Excel om du vill exportera analysdata.** Om du vill exportera data från arbetsytor som Microsoft Excel-filer (  [!DNL .xls] eller  [!DNL .xlsx]) måste Excel vara installerat och registrerat på den dator där du installerar Data Workbench. Om Excel inte har registrerats och Datan Workbench försöker få åtkomst till det för första gången visas en registreringsdialogruta. Om du är osäker på om kopian är registrerad startar du Excel manuellt och slutför registreringsprocessen om en registreringsdialogruta visas.

   >[!NOTE]
   >
   >I och med Data Workbench 6.4 har stödet för Excel 2007 upphört. Eftersom Data Workbench endast kan köras i Microsoft Windows med 64-bitarsarkitektur rekommenderar vi att du också installerar en 64-bitarsversion av Microsoft Excel.

* **Installera Adobe  [!DNL Acrobat] för utskrift av skalade arbetsytor till PDF.** Om du vill skriva ut skalade arbetsytor till Adobe PDF-format måste du ha Adobe  [!DNL Acrobat] installerat på den dator där du har installerat Data Workbench.

* **Ger åtkomst till en skrivare för utskrift av arbetsytor.** Om du vill skriva ut arbetsytor från Datan Workbench måste den dator där du installerar Data Workbench ha tillgång till en skrivare. Data Workbench kan skriva ut arbetsytor till färgskrivare eller svartvita skrivare och kräver inte PostScript-funktioner eller andra avancerade skrivarfunktioner. För bästa resultat rekommenderar Adobe att du skriver ut arbetsytor i färg.
* **Genomföra säkerhetsåtgärder.** Du bör följa företagets vanliga företagssäkerhetsregler för Data Workbench. För att Datan Workbench ska fungera i första hand behöver den bara kunna ansluta till en server (via port 80 och 443) och till servrar som samlar in data. Du kan använda Datans Workbench maskinvara för andra ändamål så länge du underhåller Datan Workbench och tilldelar minst 10 GB lagringsutrymme för Data Workbench.
* Om du vill återge visualiseringar korrekt måste datorn där du installerar workbench ha ett lämpligt **grafikkort** installerat (se Krav för grafikkort nedan).

**Datans Workbench klientkrav**

**Operativsystem**

* Microsoft Windows 7 64-bitars
* Microsoft Windows 8.1 64-bitars
* Microsoft Windows 10 64 bitar

>[!NOTE]
>
>Windows XP stöds inte för Data Workbench 6.1 och senare.

**Upplösning**

* Obligatoriskt: 1 024 x 768 (XGA)
* Rekommenderas: 1 920 x 1 200 (WUXGA)

**Grafikkort**

* Obligatoriskt: OpenGL-maskinvaruacceleration med stöd för OpenGL 3.2
* Rekommenderas: Dedikerat grafikkort (t.ex. NVIDIA- eller ATI-adapter)

**Processor**

* Obligatoriskt: 1,2 GHz eller högre Intel eller AMD
* Rekommenderas: ICore 2 Duo-klass

**RAM**

* Obligatoriskt: 2 GB
* Rekommenderas: 4 GB

**Anslutningar**

* Obligatoriskt: 512 kbit/s länk till DPU
* Rekommenderas: 2 Mbit/s eller snabbare länk till DPU

**Filsystem**

NTFS

**Disklagring**

Minst tio (10) GB ledigt hårddiskutrymme eller mer

**Utskrift**

Skrivaråtkomst (färg- eller gråskaleskrivare) för arbetsytor och rapporter för utskrift

**Övriga**

* Dedikerad mus
* Liten arbetsmiljö
* Skärm med yta på projektionsyta
