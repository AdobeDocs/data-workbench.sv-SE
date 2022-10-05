---
description: För att vissa funktioner i Report Server ska fungera måste du tillhandahålla och konfigurera maskinvara eller programvara innan du installerar.
title: Innan du börjar
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Innan du börjar{#before-you-begin}

{{eol}}

För att vissa funktioner i Report Server ska fungera måste du tillhandahålla och konfigurera maskinvara eller programvara innan du installerar.

## Krav för grundläggande rapportserver {#section-e891eaee79fe4fa98e658426dc3b2777}

De rapporter som skapas kan antingen vara PNG-bilder, XLS-kalkylblad eller e-postmeddelanden i ett filsystem. Maskinvarukraven är identiska med [data workbench-klient](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements).

Följande krav gäller för rapportservern:

* Åtkomst till filsystem för utdata av data (nätverksresurs eller lokal enhet).
* Åtkomst till konfigurerad SMTP-server.
* Microsoft Excel 2010 64-bitars eller högre installerat på [!DNL Report] Server. Se [Att tänka på vid automatisering av Office på serversidan](https://support.microsoft.com/kb/257757) för ytterligare information.

## Ytterligare krav {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Installera ett lämpligt grafikkort.** För att rapporterna ska kunna återges på rätt sätt, den dator där du installerar [!DNL Report] Servern måste ha ett lämpligt grafikkort installerat.

* **Installera Microsoft Excel för att generera rapporter som Excel-filer.** Generera och distribuera rapporter som Microsoft Excel-filer ( [!DNL .xls] eller [!DNL .xlsx]) måste rätt version av 64-bitars Microsoft Excel vara installerad och registrerad på datorn där du installerar Report Server. Om Excel inte har registrerats och Report Server försöker få åtkomst till det för första gången visas en registreringsdialogruta. Om du är osäker på om kopian är registrerad startar du Excel manuellt och slutför registreringsprocessen om en registreringsdialogruta visas.

   >[!NOTE]
   >
   >När du genererar rapporter som Excel-filer öppnar du en ny instans av Excel. Mer information om processen finns i [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).

* **Ge åtkomst till en SMTP-server för att distribuera rapporter via e-post.** Om du vill distribuera rapporter via e-post måste Report Server kunna ansluta till en SMTP-server och rätt portar till e-postvidarebefordringstjänsten måste öppnas.
