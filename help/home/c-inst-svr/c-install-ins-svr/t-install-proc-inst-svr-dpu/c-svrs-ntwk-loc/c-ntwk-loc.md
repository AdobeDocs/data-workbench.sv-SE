---
description: Adressfilen har samma syfte som ETC\HOSTS-filen på en nätverksansluten dator.
solution: Insight
title: Nätverksplatser
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nätverksplatser{#network-locations}

Adressfilen har samma syfte som ETC\HOSTS-filen på en nätverksansluten dator.

Till skillnad från HOSTS-filen, som beskriver en samling namn, innehåller adressfilen flera samlingar med namn som kallas nätverksplatser.

En nätverksplats är en namngiven samling adressdefinitioner. Varje adressdefinition i samlingen associerar ett vanligt namn med en IP-adress.

I adressfilen definieras en nätverksplats i en struktur som kallas NetworkLocation. NetworkLocation i följande exempel definierar en nätverksplats med namnet&quot;MyCorporate Intranet&quot;. Den innehåller en adressdefinition som mappar det vanliga namnet [!DNL VS01.myCompany.com] till IP-adressen &quot;10.2.1.70&quot;.

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

Så som visas i exemplet ovan består NetworkLocation-strukturen av tre huvudparametrar:

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Adresser </td> 
   <td colname="col2"> Definierar noll eller flera AddressDefinitions. Varje AddressDefintion associerar ett vanligt namn med en IP-adress. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Tilldelar NetworkLocation ett namn. Namnet som tilldelats en NetworkLocation måste vara unikt inom adressfilen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överordnad </td> 
   <td colname="col2"> <p>Anger namnet på en annan NetworkLocation vars medlemmar är inkluderade i denna NetworkLocation. Den här parametern gör att en NetworkLocation kan utöka en annan. </p> <p>Du kan ställa in parametern Parent på "DNS" för att utöka en NetworkLocation till klientens normala DNS-system. </p> <p>Exempel: Överordnad = sträng: DNS </p> <p>När DNS är överordnat försöker klienterna matcha ett vanligt namn med klientdatorns DNS-system när de inte kan matcha namnet via NetworkLocation. </p> </td> 
  </tr> 
 </tbody> 
</table>
