---
description: Filer som ingår i Datans Workbench installationspaket.
title: Filer som ingår i installationspaketet
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
exl-id: 086fb49c-d492-4670-938b-7ede70a7cd16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Filer som ingår i installationspaketet{#files-included-in-the-installation-package}

{{eol}}

Filer som ingår i Datans Workbench installationspaket.

Följande kataloger finns i Insight-paketet.

## Programfiler {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

Arbetsstationens körbara fil (**[!DNL Insight.exe]**) och stödfiler installeras som standard i den här mappen.

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Katalog </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> Den körbara filen för Datan Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span> </b> </td> 
   <td colname="col2"> Ange språk och sökväg för <span class="filepath"> Appdata </span> mapp. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>Data Workbench har nu stöd för en IME-redigerare (Input Method Editor) som en sekundär textinmatningsprocess där du kan ange internationella tecken från tangentbordet med en flytande textruta. Data workbench har stöd för engelska som standard, men gör det även möjligt att läsa in andra filer för stöd av internationella språk, till exempel ett virtuellt kinesiskt tangentbord (Pinyin IME). </p> <p>En ny ordlistefil <span class="filepath"> (Insight.zbin </span>) krävs av klientprogrammet för att stödja IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Körbar för att avinstallera Workstation och ta bort filer. </td> 
  </tr> 
 </tbody> 
</table>

## AppData-filer {#section-afddeedf8d29451f996fa46b2dfe932c}

Datafiler (**[!DNL Insight.cfg]**, profiler, certifikat, spårningsloggar och användarfiler) sparas som standard till:

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Katalog </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> Konfigurationsfilen för Datan Workbench. Definierar parametrar inom vilka Datan Workbench fungerar. Se <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Konfigurera anslutningen till Insight Server </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Bas </span> </b> </td> 
   <td colname="col2"> <p>Innehåller programfilerna för Data Workbench. </p> <p> <p>Obs! Du bör inte ta bort eller ändra någon av dessa filer. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certifikat </span> </b> </td> 
   <td colname="col2"> Innehåller certifikatfilen, <span class="filepath"> trust_ca_cert.pem </span>och det namngivna användarcertifikatet för Data Workbench. Se <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Hämta och installera det digitala certifikatet </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Konfiguration </span> </b> </td> 
   <td colname="col2"> Innehåller de filer som används för arbetsstationskonfigurationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Geografi </span></b> </td> 
   <td colname="col2"> Filer för grafisk återgivning av geografiska visualiseringar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Kalkera </span></b> </td> 
   <td colname="col2"> Loggfiler som genererats från arbetsstationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Profiler </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>Prediktiv analys</i> och andra profilkonfigurationsfiler. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Installationsguiden installerar ytterligare klientdatorer i <b> <span class="filepath"> Software/Insight </span></b> mapp. </td> 
  </tr> 
 </tbody> 
</table>
