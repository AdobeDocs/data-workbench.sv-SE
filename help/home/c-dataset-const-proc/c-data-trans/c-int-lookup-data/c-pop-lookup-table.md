---
description: Om du använder omformningarna Categorisze eller FlatFileLookup läses uppslagstabellen in i minnet och fylls i från en platt fil vars plats du anger när du definierar omformningen.
solution: Analytics
title: Fylla i uppslagstabellen
topic: Data workbench
uuid: a11f3902-8853-4d22-bbfd-b2a3d143cb7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Fylla i uppslagstabellen{#populating-the-lookup-table}

Om du använder omformningarna Categorisze eller FlatFileLookup läses uppslagstabellen in i minnet och fylls i från en platt fil vars plats du anger när du definierar omformningen.

Den platta filen som du anger måste uppfylla följande krav:

* Varje rad i filen måste representera en rad i uppslagstabellen.
* Kolumner i filen måste avgränsas med en ASCII-avgränsare. Du kan använda vilket tecken som helst som inte är ett radslutstecken och som inte visas någonstans i själva händelsedatan. När du definierar omformningen anger du vilket tecken som har använts för att avgränsa kolumnerna i den platta filen.

Om du använder en [!DNL ODBCLookup] omformning läses uppslagstabellen in i minnet och fylls i från en tabell eller vy i en [!DNL ODBC] databas som du anger. När du definierar omvandlingen måste du även ange datakällan, användarnamnet och lösenordet som data workbench-servern måste använda för att upprätta en anslutning till databasen.

>[!NOTE]
>
>Uppslagstabeller läses in när data-workbench-servern börjar skapa datauppsättningen. När de väl har skapats ska sökfiler inte ändras. Om du ändrar den platta fil eller [!DNL ODBC] tabell som används för omformningsfasen måste du omforma hela datauppsättningen. Om du ändrar en platt fil som används under loggbearbetningsfasen tillämpas nya sökdata på alla nya poster som matas in i datauppsättningen, men ändringarna tillämpas inte retroaktivt.

