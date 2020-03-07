---
description: Information om elementets punktlagerkolumner.
solution: Analytics
title: Sökfilformat för elementpunkt
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sökfilformat för elementpunkt{#element-point-lookup-file-format}

Information om elementets punktlagerkolumner.

Sökfilen för elementpunktslagret måste innehålla minst följande tre kolumner:

* **[!DNL Key]kolumn:**Den här kolumnen ska innehålla data för en vanlig nyckel, vilket gör att data-workbench-servern kan ansluta data i sökfilen till data i datauppsättningen. Kolumnen måste vara den första kolumnen i uppslagsfilen[!DNL Key]. Varje rad i den här kolumnen identifierar ett element i dimensionen.

* **[!DNL Longitude]kolumn:**Denna kolumn ska innehålla longituden för varje datapunkt i[!DNL Key]kolumnen.

* **[!DNL Latitude]kolumn:**Den här kolumnen ska innehålla latituden för varje datapunkt i[!DNL Key]kolumnen.

* **[!DNL Name]kolumn:**(Valfritt). Om du vill ange ett namn som ska visas på kartan för varje datapunkt, kan du inkludera en[!DNL Name]kolumn i sökfilen.

Varje rad i [!DNL Zip Points.txt] sökfilen innehåller en ZIP-kod i den första kolumnen följt av longitud, latitud och associerat stadsnamn.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

