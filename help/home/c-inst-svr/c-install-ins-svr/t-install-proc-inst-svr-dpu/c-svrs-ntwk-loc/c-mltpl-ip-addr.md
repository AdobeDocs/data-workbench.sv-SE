---
description: Om klienter kan nå en Insight Server via flera nätverk (till exempel via företagets intranät och Internet) måste adressfilen definiera en separat nätverksplats för varje servers IP-adresser.
title: Flera IP-adresser för en Insight-server
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# Flera IP-adresser för en Insight-server{#multiple-ip-addresses-for-an-insight-server}

Om klienter kan nå en Insight Server via flera nätverk (till exempel via företagets intranät och Internet) måste adressfilen definiera en separat nätverksplats för varje servers IP-adresser.

Om servern [!DNL VS01.myCompany.com] till exempel har IP-adressen 10.2.1.70 i ett internt nätverk och IP-adressen 65.196.125.167 på Internet, innehåller adressfilen en nätverksplats för var och en av adresserna enligt exemplet nedan:

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

När användare ansluter till en [!DNL Insight Server] använder de parametern NetworkLocation (i klientanvändargränssnittet) för att ange nätverksplatsen som de vill att serverns gemensamma namn ska matchas med. Med en adressfil med de två NetworkLocations som visas ovan skulle en användare ange parametern NetworkLocation till &quot;MyCorporate Intranet&quot; för att ansluta till [!DNL Insight Server] via det interna nätverket och till &quot;Internet&quot; för att ansluta till servern via Internet.
