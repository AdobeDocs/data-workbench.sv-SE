---
description: Exportera segment med hjälp av guiden för segmentexport
title: Guiden för segmentexport
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
exl-id: 6f42c5c6-a158-4ddd-8949-4ef55a44ed1c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---

# Guiden för segmentexport{#segment-export-wizard}

Exportera segment med hjälp av guiden för segmentexport

Guiden för segmentexport innehåller en stegvis process för att konfigurera och exportera segment i stället för att [exportera segment från en detaljtabell](https://experienceleague.adobe.com/docs/data-workbench/using/client/export-data/c-sgmt-expt.html).

## Exportera segment med guiden {#section-b30f2699dbc7490bad18512b91cb0cb3}

Om du vill öppna guiden högerklickar du på en arbetsyta och väljer **Admin** > **Guider** > **Guiden för segmentexport**.

>[!NOTE]
>
>Endast de segment som används innan guiden öppnas hämtas. Dessutom kan segmentexporter som skapats från guiden inte visa externa kommandon.

1. Välj de olika överordnade nivåerna för de dimensioner och mått som ska läggas till i exporten.

   Vilka nivåer som visas beror på vilken profil som valts. Du kan välja flera dimensionsnivåer baserat på profilen.

   ![](assets/seg_wizard_1.png)

1. Klicka på **Nästa**.
1. Markera Dimension och mått för de markerade nivåerna.

   När du t.ex. har valt Sidvy som överordnad nivå kan du välja de underordnade dimensioner och mått som är tillgängliga för export.

1. Klicka på **Nästa**.

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. Markera exportformatet och ange ett namn för exportfilen.

   ![](assets/seg_wizard_3.png)

   Typerna CSV, TSV, segmentexport och segmentexport med huvud behöver inte konfigureras ytterligare. Profilerna och målgruppsexporten, den anpassade posttjänsten och Adobe Target Export måste dock konfigureras i steg 3. Se till exempel konfigurationsfälten för profilerna och målgruppsexporten. Konfigurera de här exporttyperna och klicka på **Nästa**.

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. Konfigurera den valda exporttypen.

   Header - Om Header är True ger du fältet **Output File** namnet.

   Escape-fält - Ange som **Sant** eller **Falskt**.

   Fältordning - Välj ett fält och flytta uppåt eller nedåt för att ange ordningen i exportfilen.

   ![](assets/seg_wizard_4.png)

   Klicka på **Nästa**.

1. Visa Nivå och använda filter i den här dialogrutan. Klicka på **Nästa**. ![](assets/seg_wizard_5.png)

1. Om **CSV**, **TSV**, **Segmentexport** eller **Segmentexport med rubrik** är valt finns det tre alternativ:

   Allmän export - Utdatafilen genereras av servern i mappen Server/Export.

   ![](assets/seg_wizard_6.png)

   FTP-export - Utdatafilen överförs till den valda servern. (Serverns lista hämtas från filen FTPServerInfo.cfg.)

   ![](assets/seg_wizard_6_1.png)

   SFTP-export - Utdatafilen överförs säkert till den valda servern.

1. Klicka på **Nästa**

   **Obs!** Om den valda exporttypen är  **Profiler och Audience Export**,  **Custom Record Service** och  **Adobe Target Export**, kommer texten att vara statisk baserat på den markerade exporten.

1. Konfigurera schemaläggningsparametrar.

   **Ett** Shotcan anges till True eller False.

   **Avancerad** schemaläggning kan aktiveras och inaktiveras genom att klicka på knappen Avancerad schemakonfiguration.

   ![](assets/seg_wizard_7.png)

   Precis som när du exporterar från detaljtabellen försvinner ett foto om den avancerade inställningen är aktiverad. Klicka på **Nästa**.

1. Förhandsgranska exportfilen och klicka sedan på **Kör export**.

   ![](assets/seg_wizard_8.png)

   ![](assets/seg_wizard_8_1.png)

Följande exporttyper är tillgängliga med guiden:

**Segmentexporttyper**

* Allmän
* FTP
* SFTP

**Segmentexport med rubrik**

* Allmän
* FTP
* SFTP

**CSV-export**

* Allmän
* FTP
* SFTP

**TSV-export**

* Allmän
* FTP
* SFTP
