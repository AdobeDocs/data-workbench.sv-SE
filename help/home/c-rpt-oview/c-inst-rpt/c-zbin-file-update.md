---
description: För alla språk kräver Report Server 6.0 och senare filen insight.zbin som kopieras till rotmappen för Report Server.
title: Uppdatera rapportserver med en språkfil (.zbin-fil)
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
exl-id: a76b7c01-83f0-4cf2-97a9-07d51cc75b3c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Uppdatera rapportserver med en språkfil (.zbin-fil){#update-report-server-with-a-language-file-zbin-file}

För alla språk kräver Report Server 6.0 och senare filen insight.zbin som kopieras till rotmappen för Report Server.

Uppdatera språkfilerna för Report Server:

1. Lägg till den namnändrade filen insight.zbin i rotkatalogen ReportServer.
1. Konfigurationsfilen för rapportservern (rapportserver.cfg) kräver teckensnittsinställningar för dubbelbytespråk. Kinesiska kräver till exempel tillägg av teckensnitt med SimSun:

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. En parameter för Report Server 6.0 måste skickas i kommandoraden för lokalisering, till exempel:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Om ingen språkinställning anges används engelska som standard.

   Följ stegen för att starta ReportServer som en tjänst med språkparametrarna:

   1. Starta en kommandotolk som administratör.
   1. Navigera till installationsmappen för ReportServer.
   1. Ange följande kommando för att starta tjänsten:

      * För engelska: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * För kinesiska: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Så här kontrollerar du om ReportServer körs med rätt parametrar:

   1. Öppna Windows Service Manager.
   1. Högerklicka [!DNL Adobe Insight Report Server - Properties].

   Sökvägen till den körbara filen innehåller parametrarna:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
