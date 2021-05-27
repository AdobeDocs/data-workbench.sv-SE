---
description: Information om elementets punktlagerkolumner.
title: Sökfilformat för elementpunkt
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Sökfilformat för elementpunkt{#element-point-lookup-file-format}

Information om elementets punktlagerkolumner.

Sökfilen för elementpunktslagret måste innehålla minst följande tre kolumner:

* **[!DNL Key]kolumn:** Den här kolumnen ska innehålla data för vanlig nyckel, vilket gör att data-workbench-servern kan ansluta data i sökfilen till data i datauppsättningen. Kolumnen [!DNL Key] måste vara den första kolumnen i sökfilen. Varje rad i den här kolumnen identifierar ett element i dimensionen.

* **[!DNL Longitude]kolumn:** Den här kolumnen ska innehålla longitud för varje datapunkt i  [!DNL Key] kolumnen.

* **[!DNL Latitude]kolumn:** Den här kolumnen ska innehålla latituden för varje datapunkt i  [!DNL Key] kolumnen.

* **[!DNL Name]kolumn:** (valfritt). Om du vill ange ett namn som ska visas på kartan för varje datapunkt kan du ta med en [!DNL Name]-kolumn i sökfilen.

Varje rad i [!DNL Zip Points.txt]-sökfilen innehåller en ZIP-kod i den första kolumnen följt av longitud, latitud och associerat stadsnamn.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
