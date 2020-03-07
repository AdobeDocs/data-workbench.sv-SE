---
description: Du kan enkelt skapa en segmentexportdefinition från visualiseringen av detaljtabellen i Data Workbench-klienten.
solution: Analytics
title: Segmentexport
topic: Data workbench
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Segmentexport{#segment-export}

Du kan enkelt skapa en segmentexportdefinition från visualiseringen av detaljtabellen i Data Workbench-klienten.

Kombinera dessutom [!DNL Segment Exports] automatiskt resultaten till en enda server i stället för att producera delar av varje DPU som du måste kombinera med en extern process. Du kan skapa en segmentexportfil, spara den i [!DNL Profile Manager]och överföra utdatafilen till en valfri server.

**Konfigurera segmentexportservern**

Med den här funktionen skapas [!DNL Segment Export] en enda utdatafil på segmentexportservern, i stället för separata utdatafiler som skapas på varje DPU. Segmentexportservern är vanligtvis konfigurerad för att köras på FSU.

I katalogen Dataset i [!DNL Profile Manager]öppnar du [!DNL Segment Export.cfg] i Workstation och anger serveradressen. (Din adress kan vara ett IP-namn eller ett fullständigt domännamn.)

![](assets/segment_export_cfg.png)

Detta är IP för den Data Workbench-server som tar emot resultatet av segmentexporten. Detta är en engångsinstallation. Om det inte [!DNL Segment Export.cfg] finns någon export körs inte den.

**Konfigurera exportkataloger**

Av säkerhetsskäl måste körbara filer eller batchfiler som körs efter en segmentexport finnas i katalogen med konfigurerbara skript i segmentexportservern.

Utdata [!DNL .part] och slutliga utdata måste finnas i den konfigurerbara katalogen Exportera. Kommandot som ska köras finns i kommando- och kommandoargumenten. Instanser av %file% i kommandoargumenten ersätts med sökvägen till utdatafilen.

>[!NOTE]
>
>Ny version av Data Workbench 5.4 finns i mappen \Exporteras automatiskt. I tidigare exportkataloger som konfigurerats före version 5.4 krävdes ett prefix för Export\ före filnamnet för varje segmentexport. Det är nu överflödigt att lägga till det här prefixet.

1. Lägg till en SegmentExportServer i listan över servrar [!DNL Communications.cfg] på målservern för [!DNL Segment Exports]. (Exempel visas i rött).

   ![](assets/communications_cfg_example.png)

   Exportera katalog: Anger var du ska skicka [!DNL .part] och skriva ut filer. Detta kan vara en delad katalog.

   Skriptkatalog: Anger den katalog som alla körbara filer eller gruppfiler körs från.

1. [!DNL Access Control.cfg]på samma server lägger du till läs- och skrivåtkomst till URI /SegmentExportServer/ i klusterserverns AccessGroup:

   ![](assets/accesscontrol_cfg_example.png)

1. Ändra dina [!DNL .export] filer:

   ![](assets/segment_export_query_example.png)

1. För varje profil [!DNL Segment Export.cfg] finns den i katalogen DataSet\ med följande innehåll:

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

1. Högerklicka och välj i rubriken Detaljtabell **[!UICONTROL Create Segment Export File]**.
1. I [!DNL Save as]skriver du ett namn för [!DNL .export] filen.
1. Konfigurera parametrarna efter behov i [!DNL .export] filen.

   Alla markeringar eller filter på arbetsytan inkluderas i exportfilen.

1. Spara [!DNL .export] filen.

   Den sparade filen visas i [!DNL Profile Manager] för att du ska kunna spara den på servern. När du sparar filen på servern börjar exporten.

