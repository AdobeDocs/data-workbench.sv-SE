---
description: Säkerhetsuppdatering för Data Workbench Report Portal.
title: DWB Report Portal 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB Report Portal 2.1{#dwb-report-portal}

Säkerhetsuppdatering för Data Workbench Report Portal.

**Viktig säkerhetsuppdatering**

Rapportportalen innehåller nu starkare hash-algoritmer med stöd för saltning. Om du uppgraderar till Report Portal 2.1 lägger du till ett nytt textfält, PasswordSalt, med fältstorleken 20 tecken i databasen users.mdb. Det här fältet krävs för att lagra lösenordssaltet.
