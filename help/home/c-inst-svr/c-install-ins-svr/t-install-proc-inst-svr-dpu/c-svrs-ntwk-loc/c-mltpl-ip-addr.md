---
description: Om klienter kan nå en Insight Server via flera nätverk (till exempel via företagets intranät och Internet) måste adressfilen definiera en separat nätverksplats för varje servers IP-adresser.
title: Flera IP-adresser för en Insight-server
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# Flera IP-adresser för en Insight-server{#multiple-ip-addresses-for-an-insight-server}

{{eol}}

Om klienter kan nå en Insight Server via flera nätverk (till exempel via företagets intranät och Internet) måste adressfilen definiera en separat nätverksplats för varje servers IP-adresser.

Om server [!DNL VS01.myCompany.com] har en IP-adress på 10.2.1.70 i ett internt nätverk och en IP-adress på 65.196.125.167 på Internet, skulle adressfilen innehålla en nätverksplats för var och en av adresserna enligt exemplet nedan:

```
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
```

När användare ansluter till en [!DNL Insight Server]använder de parametern NetworkLocation (i klientgränssnittet) för att ange nätverksplatsen som de vill att serverns gemensamma namn ska matchas med. Om en adressfil till exempel har de två NetworkLocations som visas ovan skulle en användare ange NetworkLocation-parametern till &quot;MyCorporate Intranet&quot; för att ansluta till [!DNL Insight Server] via det interna nätverket och till Internet för att ansluta till servern via Internet.
