---
description: Adressfilen som är installerad på Insight Server innehåller fyra fördefinierade nätverksplatser.
solution: Analytics
title: Adressfilen som är installerad på Insight Server
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 0%

---


# Adressfilen som är installerad på Insight Server{#the-address-file-installed-on-insight-server}

Adressfilen som är installerad på Insight Server innehåller fyra fördefinierade nätverksplatser.

I proceduren i nästa avsnitt beskrivs hur du konfigurerar den här filen.

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0 är en tom, namnlös nätverksplats som du redigerar för att associera det vanliga namnet för din [!DNL Insight Server] till dess IP-adress. Om servern har flera IP-adresser skapar du ytterligare NetworkLocations.
* NetworkLocation 1 är [!DNL Insight] nätverksplatsen. Om du inte uttryckligen anger parametern NetworkLocation, [!DNL Insight] tolkas gemensamma namn via den här nätverksplatsen.

* NetworkLocation 2 är [!DNL Insight Server] nätverksplatsen. När de [!DNL Insight Servers] arbetar i ett kluster använder de den här nätverksplatsen för att matcha vanliga namn för kommunikation mellan servrar.

* NetworkLocation 3 är [!DNL Report] serverns nätverksplats. Om du inte uttryckligen anger parametern NetworkLocation, [!DNL Report] tolkas gemensamma namn via den här nätverksplatsen.

## Konfigurera adressfilen {#section-10caab9854a244e39b09071946f7bd27}

I proceduren nedan beskrivs hur du konfigurerar adressfilen för att definiera en nätverksplats (eller nätverksplatser) för din [!DNL Insight Server]dator.

1. Navigera till mappen [!DNL Addresses] i den katalog där du installerade [!DNL Insight Server] (till exempel [!DNL C:\Adobe\Server\Addresses)].

1. Leta reda på [!DNL server.address] filen och byt namn på den så att den återspeglar serverns vanliga namn. Om det gemensamma namnet till exempel var [!DNL server.mycompany.com]så skulle du byta namn på filen [!DNL server.mycompany.com.address].

1. Öppna den namnändrade filen i en textredigerare som Anteckningar.
1. Redigera NetworkLocation 0 för att ange det vanliga namnet och IP-adressen för [!DNL Insight Server] filen enligt nedan. Om servern har flera IP-adresser använder du NetworkLocation 0 för att ange serverns IP-adress i det lokala icke-routningsbara nätverket (till exempel dess plats i det interna nätverket).

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För det här värdet.. </th> 
   <th colname="col2" class="entry"> Ange </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP-adress</i> </td> 
   <td colname="col2"> <p>Den numeriska IP-adressen för <span class="keyword"> Insight Server- </span> datorn. </p> <p>Exempel: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Gemensamt namn </i> </td> 
   <td colname="col2"> <p>Det vanliga namnet som tilldelats det digitala certifikatet för <span class="keyword"> Insight Server </span>. </p> <p>Exempel: <span class="filepath"> server.mycompany.com </span></p> <p>Obs! Var noga med att skriva det här namnet exakt som det visas i certifikatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Namn på nätverksplats </i> </td> 
   <td colname="col2"> <p>Namnet som du vill tilldela till samlingen med vanliga namn och IP-adresser som representeras av denna NetworkLocation. Namnet måste vara unikt i adressfilen. </p> <p>Exempel: Företagets intranät </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Om du [!DNL Insight Server] har ytterligare IP-adresser skapar du ytterligare en NetworkLocation för varje adress. (Ett enkelt sätt att göra detta är att skapa en kopia av den NetworkLocation du skapade ovan och uppdatera IP-adressen i kopian.)

   Du kan lägga till den nya NetworkLocation i slutet av adressfilen eller infoga den mellan befintliga NetworkLocation-definitioner. (Positionen för en NetworkLocation i adressfilen är inte signifikant. men [!DNL Insight], [!DNL Insight Server]och [!DNL Report] Server NetworkLocations placeras vanligtvis i slutet av filen.)

   När du har lagt till de nödvändiga NetworkLocations gör du följande för att numrera om objekten i filen:

   1. Uppdatera antalet objekt för platsstrukturen så att den matchar det totala antalet NetworkLocation-definitioner i filen. Om filen till exempel innehåller fyra NetworkLocation-definitioner ser platsraden ut så här:

      ```
      Locations = vector: 4 items
      ```

   1. Uppdatera NetworkLocation-objektnumren så att NetworkLocations numreras i följd (med början från 0).
   Ett exempel på en adressfil som definierar en [!DNL Insight Server] med två IP-adresser finns i exemplet i det här avsnittet.

1. I nätverksplatserna [!DNL Insight] och [!DNL Report] Server redigerar du parametern Parent så som visas nedan för att ange namnet på den NetworkLocation som [!DNL Insight] och [!DNL Report] använder som standardnätverksplatser. (Ett exempel på hur den överordnade parametern ser ut när den är konfigurerad finns i exemplet i det här avsnittet.)

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   Om du [!DNL Insight Server] har en enda IP-adress och därför bara har en NetworkLocation, pekar du parametern Parent på den NetworkLocation. Om du [!DNL Insight Server] har flera IP-adresser pekar du parametern Parent på den NetworkLocation som definierar den adress som dina [!DNL Insight] - och [!DNL Report] klienter oftast ansluter till.

1. I nätverksplatsen redigerar du parametern Parent så som visas nedan för att peka på den NetworkLocation som servern använder för att matcha vanliga namn på andra [!DNL Insight Server] [!DNL Insight Servers] när den arbetar i ett kluster. (Även om den här nätverksplatsen inte används om inte en [!DNL Insight Server] används i ett kluster, är det bra att peka parametern Parent mot en nätverksplats som identifierar serverns interna IP-adress, även i en enda serverkonfiguration.)

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

I följande exempel visas en ifylld adressfil. Den här filen definierar fem nätverksplatser.

* NetworkLocation-objekten 0 och 1 definierar nätverksplatser med namnen&quot;MyCorporateIntranet&quot; och&quot;Internet&quot;. Dessa nätverksplatser definierar två olika IP-adresser för en server med namnet [!DNL VS01.myCompany.com].
* NetworkLocation-objekt 2 är [!DNL Insight] nätverksplatsen. Det här är standardnätverksplatsen som används av [!DNL Insight]. I det här exemplet ärver nätverksplatsen [!DNL Insight] dess AddressDefinitions från NetworkLocation på Internet.

* NetworkLocation-objekt 3 är [!DNL Insight Server] nätverksplatsen. Detta är standardnätverksplatsen [!DNL Insight Server] som används vid kommunikation med andra servrar i ett kluster. I det här exemplet ärver nätverksplatsen [!DNL Insight Server] dess AddressDefinitions från NetworkLocation för &quot;MyCorporate Intranet&quot;.

* NetworkLocation-objekt 4 är [!DNL Report] serverns nätverksplats. Det här är standardnätverksplatsen som används av [!DNL Report]. I det här exemplet ärver [!DNL Report] servernätverksplatsen sina AddressDefinitions från NetworkLocation på Internet.

   ```
   Locations = vector: 5 items 
     0 = NetworkLocation:  
       Addresses = vector: 1 items 
         0 = AddressDefinition:  
           Address = string: 10.2.1.70 
           Name = string: VS01.myCompany.com 
       Name = string: MyCorporateIntranet 
       Parent = string:  
   
     1 = NetworkLocation:  
       Addresses = vector: 1 items 
         0 = AddressDefinition:  
           Address = string: 65.196.125.167 
           Name = string: VS01.myCompany.com 
       Name = string: Internet 
       Parent = string: 
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```

