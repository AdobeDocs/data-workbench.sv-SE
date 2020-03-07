---
description: Följ de här stegen för att uppgradera till Data Workbench v6.5.
title: Uppgraderar 6.4 till 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Uppgraderar 6.4 till 6.5{#upgrading-to}

Följ de här stegen för att uppgradera till Data Workbench v6.5.

## Krav och rekommendationer för uppgradering {#section-8704a9ac358246cd81233dd0982d534f}

Följ dessa krav och rekommendationer när du uppgraderar till Data Workbench 6.5.

* Ändringar i **[!DNL Components for Processing Servers\Communications.cfg]** filen kräver att du uppdaterar den här filen för DWB 6.5-versionen. Posterna *SourceListServer*, *SegmentExportServer* och *NormalizeServer* har tagits bort. (DPU:er ska inte köra *källista*, *segmentexport* eller *normalisera servrar*. )

* Korrelationskord, korrelationsmatris, associationskord, associationsmatris, känslighetspoäng och visualiseringar för bästa passform är nu visualiseringar i flera omgångar.

   Om det finns mer än en visualisering för flera omgångar i en arbetsyta, kommer rapportservern som standard inte att kunna generera rapporter. Felkod:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Undvik det här felet genom att uppdatera din [!DNL ReportServer.cfg] fil eller lägga till raden i den befintliga filen i *rapportavsnittet* .

   ```
   Max Multipass Per Slice = int: n
   ```

   där n är det högsta antalet visualiseringar med flera omgångar som stöds av Report Server i en arbetsyta.

