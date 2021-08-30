---
description: Nya funktioner, korrigeringar och kända fel i Data Workbench 6.7.
title: Versionsinformation om Data Workbench 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---

# Versionsinformation om Data Workbench 6.7{#data-workbench-release-notes}

Nya funktioner, korrigeringar och kända fel i Data Workbench 6.7.

## Versionsinformation om Data Workbench 6.7 {#topic-7655534554ac4a4b816af1bd73b06aad}

Nya funktioner, korrigeringar och kända fel i Data Workbench 6.7.

## Nya funktioner i version 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Ny autentiseringsmodell för Data Workbench Workstation (IMS-integrering)**

Data Workbench Workstation har nu stöd för användarautentisering via användarnamn och lösenord. Med den här nya metoden kan administratörer skapa och hantera egna användarkonton, så att man slipper kontakta kundtjänst.

Mer information finns i [Självetablering av användare](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html).

**Platt filsökning**

Data Workbench Workstation har nu stöd för användarautentisering via användarnamn och lösenord. Med den här nya metoden kan administratörer skapa och hantera egna användarkonton, så att man slipper kontakta kundtjänst.

Vid en platt filsökning lästes hela filen in i minnesbuffertar, minnesanvändningen blottas och prestandaproblem skapas för andra undersystem. Filerna kan nu mappas och cachelagras i Windows, vilket optimerar minnesanvändningen genom att ställa in *Memory MMappad Lookup Files* på true i [!DNL MemorySettings.cfg].

Mer information finns i [Självetablering av användare](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html).

**Minnesanvändning**

Du kan nu inaktivera användningen av stora sidor genom att ange *Använd stora sidor* till false i [!DNL MemorySettings.cfg]. Mer information finns i [Övervaka minnesanvändning](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html).

**Säkerhetsutbildare**

Stöd för ECDHE och DHE har lagts till.

E-postsupport i [!DNL User List.cfg]

Stöd för e-postattribut har lagts till i [!DNL User List.cfg]. Mer information finns i [Användaradministration av gruppmedlemmar](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html).

**Hjälp-menyn**

På hjälpmenyn visas nu en genväg till Öppna certifikatkatalog.

**`TargetBulkUpload`export**

URL:er kommer att anges i slutet av exportspårningsfilen och `targetbulkuploadexportname.log.completed`-filen för att spåra posten för fastnade batchar.

En ny fil, [!DNL TargetBulkUpload.cfg], har angetts för att konfigurera maximalt tidsgränsintervall (i minuter). Filen finns i [!DNL Server\Admin\Export\].

## Korrigeringar {#section-160baf6ea04c45a993777ee4260691ed}

* Ett problem har korrigerats där Campaign Clickthrough-dimensionen visade uppblåsta värden.
* Ett problem med att generera Excel-filer från rapportservern har korrigerats.
* RC4-chiffrering är nu inaktiverat som standard.
* Ett problem som gjorde att Datans Workbench arbetsstation kraschade när ett dimensionselement lades till i en värdeförklaringstabell har åtgärdats.
* Korrigerade ett problem med Data Workbench för AAM export som orsakade timeout.
* Ett problem som gjorde att Datans Workbench arbetsstation kraschade när en användare utan tillräcklig åtkomstnivå sparade arbetsytan på servern har åtgärdats.
* Ett problem har korrigerats där datumformatet i [!DNL report.cfg] var felaktigt eller inte lokaliserat.
* Korrigerade ett problem med mobil- och produktraderna i AVRO-flödet som visade förvirrande information.
* Ett problem som förhindrade sorteringen av `*.1cd`- och `*.1ad`-filer i [!DNL order.txt] har åtgärdats.

* Alternativet Skicka till server har inaktiverats för algoritmen Förväntningsmaximering när kluster körs.
* Korrigerade ett problem med den körbara filen `TargetBulkUpload` som inte kördes fullständigt.

## Kända fel {#section-d76322bdac5043f087ab303dc68b8fff}

* När du loggar ut rensas [!DNL user cache.db]-filen.
* IMS-användarens e-postadresser som innehåller &#39;+&#39; eller &#39;%&#39;-tecken stöds inte.
* Användaren kan inte logga ut på grund av ett anslutningsfel. Du kan lösa det genom att logga ut i offlineläge.
* Inloggningsfönstret för IMS återges inte korrekt på viss maskinvara med hög upplösning och hög DPI. Du kan lösa det genom att högerklicka på [!DNL Insight.exe] och navigera till **[!UICONTROL Properties]** > **[!UICONTROL Compatability]** och sedan markera kryssrutan **[!UICONTROL Override high DPI scaling behavior]**.

## Krav för uppgradering {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Uppdatera [!DNL trust_ca_cert.pem] på Insight-servrarna som ingår i byggpaketet.
1. Uppdatera serverns och rapportserverns certifikat genom att hämta nya certifikat från [https://aap.adobe.com](https://aap.adobe.com).
1. Uppdatera Workstation och Report Server automatiskt genom att manuellt uppdatera [!DNL trust_ca_cert.pem] för båda genom att hämta dem från licensservern.
1. Sensorns automatiska uppdateringsfunktion kräver version 5.0 för att kunna kommunicera med Insight Server version 6.70. Dessutom måste sensorns [!DNL trust_ca_cert.pem] uppdateras manuellt genom att hämtas från licensservern.

## Systemuppdateringar {#section-c1b4949ea734440aa62658ac313261db}

Nya filer:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

Bland de uppdaterade filerna finns:

1. [!DNL trust_ca_cert.pem] för alla komponenter.
1. [!DNL Access Control.cfg] för att stödja IMS-konfiguration.
1. [!DNL Base\Context\meta.cfg] för att ha stöd för formaten Startdatum och Slutdatum i  [!DNL Report.cfg]

1. Tillägg till [!DNL Insight.cfg] som stöder proxy för IMS-autentisering:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Se [arkiverad versionsinformation](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) för Data Workbench 5.3 till 5.52.
