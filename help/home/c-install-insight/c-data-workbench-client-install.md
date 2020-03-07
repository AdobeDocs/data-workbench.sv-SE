---
description: Följande är krav och rekommendationer för installation av arbetsstationen (klienten) i Data Workbench.
solution: Analytics
title: Krav på arbetsstation
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Krav på arbetsstation{#workstation-requirements}

Följande är krav och rekommendationer för installation av arbetsstationen (klienten) i Data Workbench.

Mer information om ytterligare systemkrav för Data Workbench finns i [Serversystemkrav](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) .

>[!IMPORTANT]
>
>Server-, rapportserver- och klientkomponenterna uppgraderas för att köras på 64-bitars Windows-operativsystem.

**Innan du börjar**

Kontrollera att du har utfört de här uppgifterna innan du installerar Data Workbench Workstation (Client):

* **Lägg till** ***undantagna processer*** för *MS System Center Endpoint Protection i Windows 2012-servrar* för följande körbara filer:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Detta ger behörighet för&quot;vit lista&quot; för dessa korsande körbara filer.

* **Installera Microsoft Excel om du vill exportera analysdata.** Om du vill exportera data från arbetsytor som Microsoft Excel-filer ( [!DNL .xls] eller [!DNL .xlsx]) måste Excel vara installerat och registrerat på den dator där du installerar Data Workbench. Om Excel inte har registrerats och Data Workbench försöker få åtkomst till det för första gången visas en registreringsdialogruta. Om du är osäker på om kopian är registrerad startar du Excel manuellt och slutför registreringsprocessen om en registreringsdialogruta visas.

   >[!NOTE]
   >
   >I och med lanseringen av Data Workbench 6.4 har stödet för Excel 2007 upphört. Eftersom Data Workbench endast kan köras i Microsoft Windows med 64-bitarsarkitektur rekommenderar vi att du också installerar en 64-bitarsversion av Microsoft Excel.

* **Installera Adobe[!DNL Acrobat]för utskrift av skalade arbetsytor till PDF.** Om du vill skriva ut skalade arbetsytor till Adobe PDF-format måste Adobe vara installerat på den dator där du installerade Data Workbench [!DNL Acrobat] .

* **Ger åtkomst till en skrivare för utskrift av arbetsytor.** Om du vill skriva ut arbetsytor från Data Workbench måste datorn som du installerar Data Workbench ha tillgång till en skrivare. Data Workbench kan skriva ut arbetsytor på färg- eller svartvita skrivare och kräver inte PostScript-funktioner eller andra avancerade skrivarfunktioner. Adobe rekommenderar att du skriver ut arbetsytor i färg för att få bästa möjliga resultat.
* **Genomföra säkerhetsåtgärder.** Du bör följa ditt företags vanliga företagssäkerhetspolicyer för Data Workbench-datorer. Data Workbench har som huvudsyfte bara möjlighet att ansluta till en server (via port 80 och 443) och till alla servrar som samlar in data. Du kan använda maskinvaran för Data Workbench för andra syften så länge du underhåller programvaran Data Workbench och tilldelar minst 10 GB lagringsutrymme för Data Workbench.
* För att visualiseringar ska kunna återges korrekt måste rätt **grafikkort** vara installerat på datorn som du installerar workbench på (se Krav för grafikkort nedan).

**Krav för Data Workbench-klient**

**Operativsystem**

* Microsoft Windows 7 64-bitars
* Microsoft Windows 8.1 64-bitars
* Microsoft Windows 10 64 bitar

>[!NOTE]
>
>Windows XP stöds inte för Data Workbench 6.1 och senare versioner.

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

