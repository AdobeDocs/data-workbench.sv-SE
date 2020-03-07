---
description: Följ de här stegen för att starta introduktionsprocessen för Adobe Data Workbench (DWB), en komponent i Adobe Analytics Premium (AAP).
title: Grundläggande introduktionsinstruktioner för DWB Managed Services
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Grundläggande introduktionsinstruktioner för DWB Managed Services{#basic-onboarding-instructions-for-dwb-managed-services}

Följ de här stegen för att starta introduktionsprocessen för Adobe Data Workbench (DWB), en komponent i Adobe Analytics Premium (AAP).

Dessa introduktionsanvisningar är till för kunder som implementerar Data Workbench med en enda rapportserie som använder Adobes hanterade tjänster utan konsulttjänster. Om du är en ny AAP-kund som implementerar DWB blir Adobe Onboarding-teamet din första kontakt. Om du uppgraderar från Adobe Analytics-standard eller från en tidigare version av DWB får du hjälp av en Customer Success Manager från Adobe.

## Information om introduktion: Vad vi behöver från dig {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe kommer att kontakta dig för att

* Identifiera en primär användare för DWB för att generera ett certifikat specifikt för den användaren i nätverkskatalogen. Huvudanvändaren fungerar också som kontaktperson för att interagera med Adobes kundtjänst.
* Identifiera den rapportsvit som ska läsas in i DWB.

Adobe Digital Marketing-teamen använder sedan informationen för att skapa profiler, ställa in konton och leverera en konfigurationsfil för DWB.

**Adobes introduktionsuppgifter**

* Adobes kundtjänst skapar ett DWB-licensierat konto. Adobes kundtjänst genererar ett DWB-certifikat för den primära användaren.
* Adobes kundtjänst definierar den primära användaren som en&quot;användare som stöds&quot;, den person som identifieras för samtal som stöds och problemlösning.
* Adobe Customer Care läser in programpaket till DWB-licensen och programvaruportalen (SoftDocs/Software and Docs profile) som ska laddas ned till din organisation.
* Adobe TechOps-teamet förbereder produktions- och utvecklingsmiljöerna och deras profiler (per kontrakt) för DWB.
* Adobe TechOps-teamet konfigurerar dataflöden och profilhanteringsskript.
* Adobe TechOps-teamet skapar och skickar DWB-konfigurationsfilen (Insight.cfg) till Adobe Onboarding-teamet som ansvarar för startuppgifter som är kopplade till din organisation.

När du har anpassat dataflödena och genererat autentiseringsuppgifter, certifikat och en profilkonfiguration skickar Adobes kundtjänst konfigurationsfilen och autentiseringsuppgifterna till nästa steg.

## Få åtkomst till dina anpassade installationsfiler {#section-26962bf57fef435dbd1c5486d4b6f688}

Du får dessa installationsfiler från Adobes kundtjänst för att installera DWB Workstation på klientdatorn.

* Din anpassade DWB-konfigurationsfil (Insight.cfg)

   Den här konfigurationsfilen på klientdatorn kommer att innehålla anslutningar till dina hanterade DWB-servrar.

* Inloggningsuppgifter för licensieringsportalen för att hämta DWB Setup Wizard och det nödvändiga certifikatet (.pem-filen) med namnet på din primära användare.

**Hämta ytterligare installationsfiler**

1. Bläddra till: license.visualsciences.com för att ladda ned ditt licenscertifikat och den körbara filen för DWB Setup Wizard.
1. Ange din organisation (kontonamn), namnet på den primära användaren och lösenordet som du fick från Adobes kundtjänst och klicka sedan på Logga in.

   >[!NOTE]
   >
   >Din webbläsare kan uppmana dig att presentera ett digitalt certifikat just nu. Om så är fallet klickar du på Avbryt för att stänga dialogrutan.

1. Leta reda på certifikatet som utfärdats för din instans av Adobe Data Workbench (`<PrimaryUser>`.pem) i hämtningsavsnittet och hämta.
1. Leta reda på standardklientinstallationsprogrammet i hämtningsavsnittet för att hämta DWB Setup Wizard (InsightSetup-x.xx.exe file).
1. När du har tagit emot och laddat ned filer från Adobes kundtjänst kör du installationsguiden för DWB för att installera arbetsstationsprogramvaran på klientdatorn.

>[!NOTE]
Installationsguiden för DWB hjälper dig att installera DWB-klientarbetsstationen och hitta filerna Insight.cfg och `<PrimaryUser>`.pem som ska placeras i de mappar som behövs. Filen Insight.cfg finns i filen Insight.exe som finns på din installerade klientdator. Filen `<PrimaryUser>`.pem finns i mappen Certificates med filen trust_ca_cert.pem. Alla certifikat- och konfigurationsfiler måste finnas för att DWB ska fungera.

Mer information finns i installationsguiden för [DWB](https://docs.adobe.com/content/help/en/data-workbench/using/install/workstation-setup/install-setup.html).

## Anslutning till DWB-servrar {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

Dina hanterade servrar identifieras i filen Insight.cfg som du får från Adobes kundtjänst och finns på din klientdator. Adobe TechOps konfigurerar dina servrar och Adobe Customer Care lägger till referenser till dessa hanterade servrar och profiler i filen Insight.cfg innan den skickas till dig. (Konfigurationen av anslutningar till servern i steg 12 i dokumentationen för DWB Setup Wizard slutförs.)

>[!NOTE]
På arbetsytan Konfiguration av arbetsstation på DWB-klientarbetsstationen kan du se dina anslutna servrar och profiler.

**Adobes hanterade tjänster**

・ Adobe TechOps hanterar infrastrukturen inklusive nätverk, datacenter, servrar och lagring. Infrastrukturövervakning och åtgärder vid larm sker dygnet runt för varningar som kräver TechOps-åtgärd. För andra varningar kommer TechOps att meddela Adobes kundtjänst att de ska samordna med dig.

・ Adobe TechOps kommer att utföra underhåll och firmware-uppdateringar för dina hanterade servrar. För underhåll som kan orsaka driftstopp får du meddelanden om underhåll från kundtjänst minst två veckor i förväg. Adobe TechOps kommer att tillgodose behoven så snabbt som möjligt. Meddelandet är beroende av hur brådskande det är och kommer att lösas när schemat är känt.

・ Adobe TechOps sätter upp en schemalagd uppgift som automatiskt hanterar data. Data från analysflöden flyttas till DWB för bearbetning och omvandling varje kväll med början kl. 21:00 för rapportsviten.

・ Adobe TechOps kommer att bearbeta andra av Adobes hanterade tjänster: säkerhetskopiering av data, FTP-konton, arkivering av data och dataöverföring vid behov.

・ Adobe TechOps konfigurerar det primära produktionsklustret så att det innehåller tre månaders rullande data som ska återställas och bearbetas varje månad. Uppdateringar av uppslag (Geography, DeviceAtlas, Standard Classifications) kommer också att utföras som en del av ombearbetningen. Som standard körs uppgiften den första fredagen i varje månad. Vid behov kan schemat ändras av kundtjänst.

Mer information får du av [Adobes kundtjänst](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
