---
description: Om du vill ansluta till en data workbench-server måste Report Server ha behörighet att komma åt den servern.
title: Aktivera åtkomst till Data Workbench Server
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# Aktivera åtkomst till Data Workbench Server{#enabling-access-to-the-data-workbench-server}

Om du vill ansluta till en data workbench-server måste Report Server ha behörighet att komma åt den servern.

Du ger åtkomst till en data workbench-server genom att lägga till Report Servers vanliga namn (som tilldelats på Report Servers digitala certifikat) till serverns åtkomstkontrollfil.

>[!NOTE]
>
>När du arbetar i en klustrad miljö bör Report Server konfigureras för att komma åt den överordnad data workbench-servern för att undvika synkroniseringsproblem. I data workbench kan du visa information om hur du bearbetar servrar i klustret med hjälp av menyalternativet [!DNL Related Servers] i [!DNL Servers Manager]. Mer information om [!DNL Servers Manager] finns i kapitlet Administrativa gränssnitt i *Datans Workbench användarhandbok*.

I proceduren nedan beskrivs hur du manuellt lägger till Report Server i åtkomstkontrollsfilen på en data workbench-server. Om du vill uppdatera åtkomstkontrollsfilen på det här sättet måste du ha tillgång till filsystemet på den dator där data workbench-servern är installerad.

Du kan också uppdatera serverns åtkomstkontrollfil med [!DNL Server Files Manager] i data workbench. För att göra detta måste din data workbench-klient ha administratörsbehörighet på servern.

Mer information om [!DNL Server Files Manager] finns i kapitlet Administrativa gränssnitt i *Datans Workbench användarhandbok*.

**Konfigurera åtkomst till en data workbench-server**

1. Gå till mappen Access Control i den katalog där du installerade data workbench-servern (InsightServer64.exe).

   Exempel: [!DNL C:\Adobe\Server\Access Control]

1. Öppna [!DNL Access Control.cfg] i en textredigerare som Anteckningar.
1. Leta reda på [!DNL Report Server AccessGroup] och lägg till det vanliga namnet [!DNL Report Server’s] för den här gruppen så som det markeras i följande filfragment. (Skriv det vanliga namnet exakt som det visas på det digitala certifikatet [!DNL Report Server’s].)

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. Spara filen.
