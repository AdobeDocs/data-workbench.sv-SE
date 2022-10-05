---
description: Följ de här stegen för att uppgradera till Data Workbench v6.5.
title: Uppgraderar 6.4 till 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
exl-id: bcfd1ab1-2fb8-4bcd-b6c9-329143274ca4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Uppgraderar 6.4 till 6.5{#upgrading-to}

{{eol}}

Följ de här stegen för att uppgradera till Data Workbench v6.5.

## Uppgraderingskrav och Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Följ dessa krav och rekommendationer när du uppgraderar till Data Workbench 6.5.

* Ändringar i **[!DNL Components for Processing Servers\Communications.cfg]** kräver att du uppdaterar den här filen för DWB 6.5-versionen. The *SourceListServer*, *SegmentExportServer* och *NormalizeServer* poster togs bort. (DPU:er ska inte köras *källista*, *segmentexport*, eller *normalisera servrar*. )

* Korrelationskord, korrelationsmatris, associationskord, associationsmatris, känslighetspoäng och visualiseringar för bästa passform är nu visualiseringar i flera omgångar.

   Om det finns mer än en visualisering för flera omgångar i en arbetsyta, kommer rapportservern som standard inte att kunna generera rapporter. Felkod:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Undvik det här felet genom att uppdatera [!DNL ReportServer.cfg] eller lägg till den här raden i din befintliga fil i *Rapportering* -avsnitt.

   ```
   Max Multipass Per Slice = int: n
   ```

   där n är det högsta antalet visualiseringar med flera omgångar som stöds av Report Server i en arbetsyta.
