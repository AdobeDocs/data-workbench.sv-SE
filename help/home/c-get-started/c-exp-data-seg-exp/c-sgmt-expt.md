---
description: Du kan enkelt skapa en segmentexportdefinition från detaljtabellvisualiseringen i Data Workbench Client.
title: Segmentexport
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Segmentexport{#segment-export}

Du kan enkelt skapa en segmentexportdefinition från detaljtabellvisualiseringen i Data Workbench Client.

Dessutom kombinerar [!DNL Segment Exports] automatiskt resultaten till en enda server, i stället för att generera delar av varje DPU som du måste kombinera med en extern process. Du kan skapa en segmentexportfil, spara den i [!DNL Profile Manager] och överföra utdatafilen till en valfri server.

**Konfigurera segmentexportservern**

Funktionen [!DNL Segment Export] skapar en enda utdatafil på segmentexportservern i stället för separata utdatafiler som skapas på varje DPU. Segmentexportservern är vanligtvis konfigurerad för att köras på FSU.

Öppna [!DNL Segment Export.cfg] i katalogen Dataset i [!DNL Profile Manager] i Workstation och ange serveradressen. (Din adress kan vara ett IP-namn eller ett fullständigt domännamn.)

![](assets/segment_export_cfg.png)

Detta är IP för den Data Workbench som tar emot resultatet av segmentexporten. Detta är en engångsinstallation. Om [!DNL Segment Export.cfg] inte finns körs inte exporter.

**Konfigurera exportkataloger**

Av säkerhetsskäl måste körbara filer eller batchfiler som körs efter en segmentexport finnas i katalogen med konfigurerbara skript i segmentexportservern.

Utdata för [!DNL .part] och slutliga utdata måste finnas i den konfigurerbara exportkatalogen. Kommandot som ska köras finns i kommando- och kommandoargumenten. Instanser av %file% i kommandoargumenten ersätts med sökvägen till utdatafilen.

>[!NOTE]
>
>Mappen \Exports är ny i Data Workbench 5.4 och skapas automatiskt. I tidigare exportkataloger som konfigurerats före version 5.4 krävdes ett prefix för Export\ före filnamnet för varje segmentexport. Det är nu överflödigt att lägga till det här prefixet.

1. Lägg till en SegmentExportServer i listan över servrar i [!DNL Communications.cfg] på målservern för [!DNL Segment Exports]. (Exempel visas i rött).

   ![](assets/communications_cfg_example.png)

   Exportera katalog: Anger var [!DNL .part]- och utdatafiler ska skickas. Detta kan vara en delad katalog.

   Skriptkatalog: Anger den katalog som alla körbara filer eller gruppfiler körs från.

1. [!DNL Access Control.cfg]på samma server lägger du till läs- och skrivåtkomst till URI /SegmentExportServer/ i klusterserverns AccessGroup:

   ![](assets/accesscontrol_cfg_example.png)

1. Ändra dina [!DNL .export]-filer:

   ![](assets/segment_export_query_example.png)

1. För varje profil finns [!DNL Segment Export.cfg] i katalogen Dataset med följande innehåll:

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Kontrollera att katalogerna i Exportera katalog och Skriptkatalog finns.

   Endast körbara filer och gruppfiler i skriptkatalogen kan köras som kommando för en segmentexport.

**Skapa en segmentexportfil**

1. I en arbetsyta skapar du en detaljtabell med delmängder av data (Visualisering > Detaljtabell) och lägger till attribut.
1. Gör markeringar på arbetsytan om du vill. (Alla markeringar eller filter tillämpas på exporten.)

   ![](assets/create_segment_export_file.png)

1. Högerklicka i detaljtabellhuvudet och välj **[!UICONTROL Create Segment Export File]**.
1. I [!DNL Save as] anger du ett namn för filen [!DNL .export].
1. Konfigurera parametrarna efter behov i [!DNL .export]-filen.

   Alla markeringar eller filter på arbetsytan inkluderas i exportfilen.

1. Spara [!DNL .export]-filen.

   Den sparade filen visas i [!DNL Profile Manager] så att du kan spara den på servern. När du sparar filen på servern börjar exporten.
