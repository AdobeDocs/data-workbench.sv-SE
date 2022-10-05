---
description: Information om de parametrar som krävs för Sensor txlogd.conf.
title: Obligatoriska parametrar
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 0%

---

# Obligatoriska parametrar{#required-parameters}

{{eol}}

Information om de parametrar som krävs för Sensor txlogd.conf.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> I den här parametern.. </th> 
   <th colname="col2" class="entry"> Ange... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>En teckensträng som unikt identifierar detta <span class="wintitle"> Sensor</span>. </p> <p> <span class="wintitle"> Sensor</span> kopplar SensorID till varje händelsepost som skickas till <span class="keyword"> data workbench-server</span>. Med SensorID kan händelsedata från den här webbservern särskiljas från händelsedata som fångas in av andra <span class="wintitle"> Sensorer</span>. </p> <p>Även om ett SensorID kan bestå av en valfri teckensträng är namnet på webbservern vars händelser <span class="wintitle"> Sensor</span> används för hämtning. Om du använder servernamnet som SensorID är det enkelt att fastställa källan för en händelse under analysfasen. SensorID är också unikt i implementeringen. </p> <p>Exempel: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>Adressen till <span class="keyword"> data workbench-server</span> som <span class="wintitle"> Sensor</span> skickar händelsedata. </p> <p>Obs!  <p>När du arbetar i en klustermiljö <span class="wintitle"> Sensor</span> bör konfigureras för att komma åt överordnad <span class="keyword"> data workbench-server</span> för att undvika synkroniseringsproblem. I Datan Workbench kan du visa information om bearbetningen <span class="keyword"> data workbench-servrar</span> i klustret med hjälp av menyalternativet Relaterade servrar i <span class="wintitle"> Serverhanteraren</span>. Mer information om <span class="wintitle"> Serverhanteraren</span>, se <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Guide</i>. </p> <p>Om webbservern kan matcha servernamn via DNS kan du ange serverns adress efter namn. Annars måste du ange serverns numeriska IP-adress. </p> <p>Exempel: <span class="filepath"> ServerAddress 10.1.0.7</span> eller </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Om <span class="wintitle"> Sensor</span> kommunicerar med <span class="keyword"> data workbench-server</span> med HTTP eller HTTPS. Ange som"på" för HTTPS eller"av" för HTTP. </p> <p>Exempel: <span class="filepath"> SSL på</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Den port som <span class="keyword"> data workbench-server</span> lyssnar efter händelsedata. </p> <p>Exempel: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Krävs bara om SSL-parametern är inställd på "on". </p> <p>Det vanliga namnet på <span class="keyword"> data workbench-server</span> som <span class="wintitle"> Sensor</span> skickar händelsedata. </p> <p>Värdet du anger måste exakt matcha det vanliga namnet som visas på <span class="keyword"> data workbench-server</span> licenscertifikat. </p> <p>Exempel: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Krävs bara om SSL-parametern är inställd på "on". </p> <p>Den katalog där certifikatutfärdaren (<span class="filepath"> trust_ca_cert.pem</span>) finns </p> <p>Exempel: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Krävs inte för <span class="wintitle"> Sensor</span> installationer på Microsoft Windows 2000- eller 2003 Server-datorer med IIS-version 5.x eller 6.x. </p> <p>Det fullständiga kvalificerade namnet på diskköfilen. </p> <p>Även om du kan ge den här filen valfritt namn namnges köfilen som standard <span class="filepath"> VisualSensor.dat</span>. </p> <p>För <span class="wintitle"> Sensor</span> vid Unix-installationer kan du montera filen var som helst. I Windows som kör en Java-webbserver måste du placera den här filen i samma katalog som sändaren. För alla andra webbservrar bör den här filen finnas i katalogen /var/queue. </p> <p>Exempel: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Obs! Se till att enheten som du tilldelar den här filen har tillräckligt med ledigt utrymme för en kö med den storlek som du behöver. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Ett heltal som representerar storleken på diskköfilen i MB. </p> <p>För <span class="wintitle"> Sensor</span> installeras i Microsoft Windows. Köfilen skapas i samma katalog som sändaren och har ett namn <span class="filepath"> Diskq2000.log</span>. </p> <p>I följande exempel ställs storleken på kön in på 200 MB: </p> <p>QueueSize 200 </p> <p>I följande exempel ställs storleken på kön in på 2 GB: </p> <p>Köstorlek 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
