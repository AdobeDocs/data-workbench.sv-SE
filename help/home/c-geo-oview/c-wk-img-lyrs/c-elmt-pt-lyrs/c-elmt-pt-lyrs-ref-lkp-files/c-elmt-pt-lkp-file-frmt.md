---
description: Information om elementets punktlagerkolumner.
title: Sökfilformat för elementpunkt
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Sökfilformat för elementpunkt{#element-point-lookup-file-format}

{{eol}}

Information om elementets punktlagerkolumner.

Sökfilen för elementpunktslagret måste innehålla minst följande tre kolumner:

* **[!DNL Key]kolumn:** Den här kolumnen ska innehålla data för en vanlig nyckel, vilket gör att data-workbench-servern kan ansluta data i sökfilen till data i datauppsättningen. The [!DNL Key] -kolumnen måste vara den första kolumnen i sökfilen. Varje rad i den här kolumnen identifierar ett element i dimensionen.

* **[!DNL Longitude]kolumn:** Denna kolumn ska innehålla longituden för varje datapunkt i [!DNL Key] kolumn.

* **[!DNL Latitude]kolumn:** Den här kolumnen ska innehålla latituden för varje datapunkt i [!DNL Key] kolumn.

* **[!DNL Name]kolumn:** (Valfritt). Om du vill ange ett namn som ska visas på kartan för varje datapunkt kan du inkludera en [!DNL Name] -kolumnen i sökfilen.

Varje rad i [!DNL Zip Points.txt] Uppslagsfilen innehåller en ZIP-kod i den första kolumnen följt av longitud, latitud och associerat stadsnamn.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
