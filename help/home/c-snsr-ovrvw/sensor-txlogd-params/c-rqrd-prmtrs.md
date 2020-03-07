---
description: Information om de parametrar som krävs för Sensor txlogd.conf.
solution: Insight
title: Obligatoriska parametrar
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Obligatoriska parametrar{#required-parameters}

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
   <td colname="col2"> <p>En teckensträng som unikt identifierar den här <span class="wintitle"> sensorn</span>. </p> <p> <span class="wintitle"> Sensorn</span> kopplar SensorID till varje händelsepost som skickas till <span class="keyword"> data workbench-servern</span>. Med SensorID kan händelsedata från den här webbservern särskiljas från händelsedata som fångas in av andra <span class="wintitle"> sensorer</span>. </p> <p>Även om ett SensorID kan bestå av en valfri teckensträng, används namnet på webbservern vars händelser <span class="wintitle"> Sensor</span> hämtas. Om du använder servernamnet som SensorID är det enkelt att fastställa källan för en händelse under analysfasen. SensorID är också unikt i implementeringen. </p> <p>Exempel: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>Adressen till den <span class="keyword"> data workbench-server</span> som den här <span class="wintitle"> sensorn</span> skickar händelsedata till. </p> <p>Obs!  <p>När du arbetar i en klustrad miljö bör <span class="wintitle"> Sensor</span> konfigureras för att komma åt master- <span class="keyword"> data workbench-servern</span> för att undvika synkroniseringsproblem. I Data Workbench kan du visa information om bearbetningsdata- <span class="keyword"> workbench-servrar</span> i ditt kluster med hjälp av menyalternativet Relaterade servrar i <span class="wintitle"> Serverhanteraren</span>. Mer information om <span class="wintitle"> Serverhanteraren</span>finns i <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Guide</i>. </p> <p>Om webbservern kan matcha servernamn via DNS kan du ange serverns adress efter namn. Annars måste du ange serverns numeriska IP-adress. </p> <p>Exempel: <span class="filepath"> ServerAddress 10.1.0.7</span> eller </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Om <span class="wintitle"> Sensor</span> kommunicerar med <span class="keyword"> data workbench-servern</span> med HTTP eller HTTPS. Ange som"på" för HTTPS eller"av" för HTTP. </p> <p>Exempel: <span class="filepath"> SSL på</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>Den port där <span class="keyword"> data workbench-servern</span> lyssnar efter händelsedata. </p> <p>Exempel: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Krävs bara om SSL-parametern är inställd på "on". </p> <p>Det vanliga namnet på den <span class="keyword"> data workbench-server</span> som den här <span class="wintitle"> sensorn</span> skickar händelsedata till. </p> <p>Värdet du anger måste exakt matcha det vanliga namnet som visas på <span class="keyword"> data workbench-serverns</span> licenscertifikat. </p> <p>Exempel: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Krävs bara om SSL-parametern är inställd på "on". </p> <p>Den katalog där certifikatutfärdarfilen (<span class="filepath"> trust_ca_cert.pem</span>) finns </p> <p>Exempel: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Behövs inte för <span class="wintitle"> Sensor</span> -installationer på Microsoft Windows 2000- eller 2003 Server-datorer som kör IIS-version 5.x eller 6.x. </p> <p>Det fullständiga kvalificerade namnet på diskköfilen. </p> <p>Även om du kan ge den här filen valfritt namn heter köfilen <span class="filepath"> VisualSensor.dat</span>. </p> <p>För <span class="wintitle"> sensorinstallationer</span> på Unix kan du montera den här filen var som helst. I Windows som kör en Java-webbserver måste du placera den här filen i samma katalog som sändaren. För alla andra webbservrar bör den här filen finnas i katalogen /var/queue. </p> <p>Exempel: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Obs!  Se till att enheten som du tilldelar den här filen har tillräckligt med ledigt utrymme för en kö med den storlek som du behöver. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Ett heltal som representerar storleken på diskköfilen i MB. </p> <p>För <span class="wintitle"> Sensor</span> -installationer i Microsoft Windows skapas själva köfilen i samma katalog som sändaren och kallas <span class="filepath"> Diskq2000.log</span>. </p> <p>I följande exempel ställs storleken på kön in på 200 MB: </p> <p>QueueSize 200 </p> <p>I följande exempel ställs storleken på kön in på 2 GB: </p> <p>Köstorlek 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

