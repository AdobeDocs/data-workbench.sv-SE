---
description: Som standard skriver Insight Server sin datauppsättning (temp.db) till samma enhet som programfilerna för Insight Server.
title: Konfigurera platsen för datauppsättningen (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# Konfigurera platsen för datauppsättningen (temp.db){#configuring-the-location-of-the-dataset-temp-db}

Som standard skriver Insight Server sin datauppsättning (temp.db) till samma enhet som programfilerna för Insight Server.

Om du till exempel installerar [!DNL Insight Server] på enhet C skrivs datauppsättningen till enhet C.

Om du vill att [!DNL Insight Server] ska underhålla datauppsättningen på en annan enhet, eller om den datamängd du förväntar dig ska samla in kräver att flera enheter används, måste du uppdatera [!DNL Disk Files.cfg]-filen och ange var du vill att [!DNL Insight Server] ska skriva [!DNL temp.db]-filen.

**Så här konfigurerar du platsen för temp.db**

1. Navigera till mappen [!DNL Components] i den katalog där du installerade [!DNL Insight Server].

   Exempel: [!DNL C:\Adobe\Server\Components]

1. Öppna [!DNL Disk Files.cfg]-filen i en textredigerare som Anteckningar.

   Som standard innehåller den här filen en enda post i strukturen Diskfiler enligt nedan.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Om du vill ändra platsen för [!DNL temp.db] ändrar du definitionen av Diskfiler. Följande exempel visar hur du skulle redigera konfigurationen för att sprida filen [!DNL temp.db] mellan enheterna C, D och E:

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >Observera att dubbla omvända snedstreck används i filnamnen ovan. I [!DNL Insight Server]-konfigurationsfiler är det omvända snedstrecket ett escape-tecken. Den används för att uttrycka särskilda kontrollsekvenser (t.ex. \t för ett tabbtecken) i text. Om du vill visa ett faktiskt omvänt snedstreck måste du skriva det två gånger (till exempel \\) för att åsidosätta escape-funktionen. Detta gäller endast när du redigerar konfigurationsfiler i en textredigerare som Anteckningar.
