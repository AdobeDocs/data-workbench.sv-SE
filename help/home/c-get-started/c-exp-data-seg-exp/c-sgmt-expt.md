---
description: Du kan enkelt skapa en segmentexportdefinition från detaljtabellvisualiseringen i Data Workbench Client.
title: Segmentexport
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Segmentexport{#segment-export}

{{eol}}

Du kan enkelt skapa en segmentexportdefinition från detaljtabellvisualiseringen i Data Workbench Client.

Dessutom [!DNL Segment Exports] kombinerar automatiskt resultaten till en enda server, i stället för att producera delresultat på varje DPU som du måste kombinera med en extern process. Du kan skapa en segmentexportfil och spara den i [!DNL Profile Manager]och överför utdatafilen till valfri server.

**Konfigurera segmentexportservern**

The [!DNL Segment Export] en enda utdatafil skapas på segmentexportservern i stället för separata utdatafiler som skapas på varje DPU. Segmentexportservern är vanligtvis konfigurerad för att köras på FSU.

I katalogen Dataset i [!DNL Profile Manager]öppnar du [!DNL Segment Export.cfg] i Workstation och ange serveradressen. (Din adress kan vara ett IP-namn eller ett fullständigt domännamn.)

![](assets/segment_export_cfg.png)

Detta är IP för den Data Workbench som tar emot resultatet av segmentexporten. Detta är en engångsinstallation. Om [!DNL Segment Export.cfg] finns inte, exporten körs inte.

**Konfigurera exportkataloger**

Av säkerhetsskäl måste körbara filer eller batchfiler som körs efter en segmentexport finnas i katalogen med konfigurerbara skript i segmentexportservern.

The [!DNL .part] och slutresultatet måste finnas i den konfigurerbara katalogen Exportera. Kommandot som ska köras finns i kommando- och kommandoargumenten. Instanser av %file% i kommandoargumenten ersätts med sökvägen till utdatafilen.

>[!NOTE]
>
>Mappen \Exports är ny i Data Workbench 5.4 och skapas automatiskt. I tidigare exportkataloger som konfigurerats före version 5.4 krävdes ett prefix för Export\ före filnamnet för varje segmentexport. Det är nu överflödigt att lägga till det här prefixet.

1. I [!DNL Communications.cfg] på målservern för [!DNL Segment Exports]lägger du till en SegmentExportServer i listan över servrar. (Exempel visas i rött).

   ![](assets/communications_cfg_example.png)

   Exportera katalog: Anger var du ska placera [!DNL .part] och utdatafiler. Detta kan vara en delad katalog.

   Skriptkatalog: Anger den katalog som alla körbara filer eller gruppfiler körs från.

1. [!DNL Access Control.cfg]på samma server lägger du till läs- och skrivåtkomst till URI /SegmentExportServer/ i klusterserverns AccessGroup:

   ![](assets/accesscontrol_cfg_example.png)

1. Ändra dina [!DNL .export] filer:

   ![](assets/segment_export_query_example.png)

1. För varje profil visas [!DNL Segment Export.cfg] finns i katalogen Dataset med följande innehåll:

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

1. Högerklicka och välj i detaljtabellhuvudet **[!UICONTROL Create Segment Export File]**.
1. I [!DNL Save as], skriver du ett namn för [!DNL .export] -fil.
1. På [!DNL .export] -filen, konfigurera parametrarna efter behov.

   Alla markeringar eller filter på arbetsytan inkluderas i exportfilen.

1. Spara [!DNL .export] -fil.

   Den sparade filen visas i [!DNL Profile Manager] så att du kan spara på servern. När du sparar filen på servern börjar exporten.
