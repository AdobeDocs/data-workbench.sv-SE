---
description: För att vissa funktioner i Report Server ska fungera måste du tillhandahålla och konfigurera maskinvara eller programvara innan du installerar.
solution: Analytics
title: Innan du börjar
topic: Data workbench
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Innan du börjar{#before-you-begin}

För att vissa funktioner i Report Server ska fungera måste du tillhandahålla och konfigurera maskinvara eller programvara innan du installerar.

## Krav för grundläggande rapportserver {#section-e891eaee79fe4fa98e658426dc3b2777}

De rapporter som skapas kan antingen vara PNG-bilder, XLS-kalkylblad eller e-postmeddelanden i ett filsystem. Maskinvarukraven är identiska med [data workbench-klienten](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements).

Följande krav gäller för rapportservern:

* Åtkomst till filsystem för utdata av data (nätverksresurs eller lokal enhet).
* Åtkomst till konfigurerad SMTP-server.
* Microsoft Excel 2010 64-bitars eller senare installerat på [!DNL Report] Server. Mer information finns [i avsnittet Saker att tänka på vid automatisering av Office](http://support.microsoft.com/kb/257757) på serversidan.

## Ytterligare krav {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Installera ett lämpligt grafikkort.** För att rapporterna ska kunna återges på rätt sätt måste rätt grafikkort vara installerat på datorn som du installerar [!DNL Report] Server på.

* **Installera Microsoft Excel för att generera rapporter som Excel-filer.** Om du vill generera och distribuera rapporter som Microsoft Excel-filer ( [!DNL .xls] eller [!DNL .xlsx]) måste rätt version av 64-bitars Microsoft Excel vara installerad och registrerad på datorn som du installerar Report Server på. Om Excel inte har registrerats och Report Server försöker få åtkomst till det för första gången visas en registreringsdialogruta. Om du är osäker på om kopian är registrerad startar du Excel manuellt och slutför registreringsprocessen om en registreringsdialogruta visas.

   >[!NOTE]
   >
   >När du genererar rapporter som Excel-filer öppnar du en ny instans av Excel. Mer information om den här processen finns på [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).

* **Ge åtkomst till en SMTP-server för att distribuera rapporter via e-post.** Om du vill distribuera rapporter via e-post måste Report Server kunna ansluta till en SMTP-server och rätt portar till e-postvidarebefordringstjänsten måste öppnas.
