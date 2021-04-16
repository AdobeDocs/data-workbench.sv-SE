---
description: Om du använder omformningarna Categorisze eller FlatFileLookup läses uppslagstabellen in i minnet och fylls i från en platt fil vars plats du anger när du definierar omformningen.
title: Fylla i uppslagstabellen
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
exl-id: e83d9feb-44fe-4fa1-b559-e1f5606637b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Fylla i uppslagstabellen{#populating-the-lookup-table}

Om du använder omformningarna Categorisze eller FlatFileLookup läses uppslagstabellen in i minnet och fylls i från en platt fil vars plats du anger när du definierar omformningen.

Den platta filen som du anger måste uppfylla följande krav:

* Varje rad i filen måste representera en rad i uppslagstabellen.
* Kolumner i filen måste avgränsas med en ASCII-avgränsare. Du kan använda vilket tecken som helst som inte är ett radslutstecken och som inte visas någonstans i själva händelsedatan. När du definierar omformningen anger du vilket tecken som har använts för att avgränsa kolumnerna i den platta filen.

Om du använder en [!DNL ODBCLookup]-omformning läses uppslagstabellen in i minnet och fylls i från en tabell eller vy i en [!DNL ODBC]-databas som du anger. När du definierar omvandlingen måste du även ange datakällan, användarnamnet och lösenordet som data workbench-servern måste använda för att upprätta en anslutning till databasen.

>[!NOTE]
>
>Uppslagstabeller läses in när data-workbench-servern börjar skapa datauppsättningen. När de väl har skapats ska sökfiler inte ändras. Om du ändrar den platta filen eller [!DNL ODBC]-tabellen som används för omformningsfasen måste du omforma hela datauppsättningen. Om du ändrar en platt fil som används under loggbearbetningsfasen tillämpas nya sökdata på alla nya poster som matas in i datauppsättningen, men ändringarna tillämpas inte retroaktivt.
