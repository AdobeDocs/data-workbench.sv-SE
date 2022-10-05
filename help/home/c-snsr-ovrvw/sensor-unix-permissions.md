---
description: Information om Sensor UNIX-filbehörigheter som insamlarmodulen, överföringsprocessen, konfigurationsfilen och mycket annat.
title: UNIX-filbehörigheter för sensor
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
exl-id: 07cbc7df-c628-437d-9ca1-b006da8de242
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 1%

---

# UNIX-filbehörigheter för sensor{#sensor-unix-file-permissions}

{{eol}}

Information om Sensor UNIX-filbehörigheter som insamlarmodulen, överföringsprocessen, konfigurationsfilen och mycket annat.

## Samlarmodulen {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kvalitet </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Filnamn </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so (på Apache-webbservrar och IBM HTTP-servrar) </p> <p>libvisual_Sciences.so och J2EECollector.jar (på J2EE-servrar) </p> <p>aol_visual_Sciences.so (på AOL-webbservrar) </p> <p>saf_visual_sciences.so (på Sun Java-webbservrar) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardbehörigheter </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP och Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x (J2EE-, AOL- och Sun Java-webbservrar) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Läs av </p> </td> 
   <td colname="col2"> <p>Webbservern, som ibland körs som rotanvändare, men ofta körs under ett visst användarkonto </p> <p>Om webbservern körs med ett icke-rotkonto måste filens behörigheter tillåta att kontot läser den. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kör som </p> </td> 
   <td colname="col2"> <p>En underordnad process på webbservern </p> <p>Underordnade processer körs med ett användarkonto som anges i webbserverkonfigurationen. På många servrar är detta ett särskilt konto med mycket begränsad behörighet som kallas "ingen", men inte alla webbservrar använder det här kontot. Kontrollera webbserverns konfigurationsfil för att se vilket användarkonto som är inställt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Läser från </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>Filen diskQueue </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skriver till </td> 
   <td colname="col2"> Filen diskQueue </td> 
  </tr> 
 </tbody> 
</table>

## Överföringsprocessen {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kvalitet </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Filnamn </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardbehörigheter </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP-, AOL- och Sun Java-webbservrar) </p> <p>rw- rw- r— (Apache-webbservrar och J2EE-programservrar) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Läs av </td> 
   <td colname="col2"> Sändarprogrammet </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skrivet av </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## Konfigurationsfilen {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kvalitet </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Filnamn </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardbehörigheter </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP-, AOL- och Sun Java-webbservrar) </p> <p>rw- rw- r— (Apache-webbservrar och J2EE-programservrar) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Läs av </td> 
   <td colname="col2"> <p>Samlarmodulen </p> <p>Sändarprogrammet </p> <p>Administratören som ansvarar för att installera, konfigurera och underhålla sensorn </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skrivet av </td> 
   <td colname="col2"> Administratören som ansvarar för att installera, konfigurera och underhålla sensorn </td> 
  </tr> 
 </tbody> 
</table>

## Certifikatutfärdarfilen {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kvalitet </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Filnamn </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardbehörigheter </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP-, AOL- och Sun Java-webbservrar) </p> <p>rw- rw- r— (Apache-webbservrar och J2EE-programservrar) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Läs av </td> 
   <td colname="col2"> Sändarprogrammet </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skrivet av </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## Diskkön {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kvalitet </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Filnamn </td> 
   <td colname="col2"> Användardefinierad </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Standardbehörigheter </td> 
   <td colname="col2"> rw- rw- rw- (alla servertyper) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Läs av </p> </td> 
   <td colname="col2"> <p>Samlarmodulen </p> <p>Sändarprogrammet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skrivet av </p> </td> 
   <td colname="col2"> <p>Samlarmodulen </p> <p>Sändarprogrammet </p> </td> 
  </tr> 
 </tbody> 
</table>
