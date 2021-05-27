---
description: Måldatorer för Insight Server som kör tjänsten Insight Server Replication måste kunna läsa loggfilerna på den här upprepade servern.
title: Konfigurera åtkomstkontroll för måldatorer
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Konfigurera åtkomstkontroll för måldatorer{#configuring-access-control-for-target-machines}

Måldatorer för Insight Server som kör tjänsten Insight Server Replication måste kunna läsa loggfilerna på den här upprepade servern.

Åtkomst till måldatorerna beviljas med hjälp av filen [!DNL Access Control.cfg].

**Konfigurera åtkomstkontroll för  [!DNL Insight Server] måldatorer**

1. Navigera till mappen [!DNL Access Control] i den katalog där du installerade funktionen för upprepning.

   Exempel: [!DNL D:\Adobe\Repeater\Access Control]

1. Öppna [!DNL Access Control.cfg] i en textredigerare som Anteckningar.
1. Skapa en åtkomstgrupp för de [!DNL Insight Server]-datorer som måste ha åtkomst till loggfilerna på den här upprepade servern. Ge den här åtkomstgruppen ett namn som &quot;Replikeringsmål&quot;.

   Följande filfragment visar hur åtkomstgruppen ska se ut.

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. I avsnittet Medlemmar anger du IP-adressen för varje dator.
   1. Uppdatera antalet objekt för medlemsvektorn så att det återspeglar antalet datorns IP-adresser som du har infogat.
   1. I avsnittet Skrivskyddad åtkomst anger du platsen för de händelsedata som replikeringen ska ha åtkomst till. Använd snedstreck i sökvägsspecifikationen (/). Standardplatsen är mappen [!DNL Logs] på datorn för upprepning (/Logs/).
   1. Uppdatera antalet objekt för den skrivskyddade åtkomstvektorn så att det motsvarar antalet platser som du infogat.

1. Uppdatera antalet åtkomstgrupper i åtkomstkontrollsgruppsvektorn högst upp i filen så att den nya åtkomstgruppen visas.

   ```
   Access Control Groups = vector: n items
   ```

1. Spara filen.
