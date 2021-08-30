---
description: Administratörer kan ge arbetsstationsanvändare delvis möjlighet att hantera åtkomstkontroll för anpassade grupper.
title: Användaradministration för gruppmedlemsåtkomst
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 0%

---

# Användaradministration för gruppmedlemsåtkomst{#user-administration-of-group-member-access}

Administratörer kan ge arbetsstationsanvändare delvis möjlighet att hantera åtkomstkontroll för anpassade grupper.

**Självadministration av gruppmedlemmens** åtkomst ger icke-administratörer rätt att lägga till och ta bort medlemmar i en anpassad grupp. Administratören skapar en **användarlista**-fil och ställer in gruppåtkomst i filen [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) för de nya gruppmedlemmarna.

**Åtkomst till serverhanteraren**

Konfigurera filen **[!DNL User List]** och synkronisera den med filen **[!DNL Communications.cfg]** görs i arbetsytan **Serverhanteraren**.

1. Klicka på fliken **Admin** > **Datauppsättning och Profil** på skrivbordet.

1. Öppna arbetsytan **Serverhanteraren**.
1. Högerklicka >*ditt servernamn* i diagrammet och välj **Filer**.

   Serverfilerna öppnas i en tabell med kolumnerna *Arkiv*, *`<server name>`* och *Temp*.

1. **Gör** lokal genom att högerklicka i serverkolumnen för en serverfil (för den här funktionen  **[!DNL Access Control]** och  **[!DNL Components/Communications.cfg)]**.

   En vit bock visas i kolumnen **Temp**. Du kan redigera i mappen Temp. Högerklicka sedan på bockmarkeringen och **Spara till** servern. (Den blir röd när den synkroniseras med servern).

## Skapa filen User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

Administratören måste skapa en **[!DNL User List.cfg]**-fil i mappen **[!DNL Access Control]**.

1. Högerklicka** Åtkomstkontroll** i kolumnen **Tillfällig** och välj **Öppna** > **Mapp**. ![](assets/6_4_workstation_groups_3.png)

   Mappen Åtkomstkontroll i mappen **Temp** öppnar en lista över en enskild **[!DNL Access Control.cfg]**-fil.

1. Lägg till ytterligare en textfil i den här mappen och ge den namnet **[!DNL User List.cfg]** (bredvid **[!DNL Access Control.cfg]**).

1. Lägg till följande parametrar i **[!DNL User List.cfg]**-filen.

Användarlistfilen ska innehålla en vektor med **AccessGroup**-objekt och varje **AccessGroup**-objekt ska ha ett namn och en vektor med strängar som heter **Medlemmar**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Du kan sedan redigera och lägga till användare i arbetsstationsvyn i filen **[!DNL User List.cfg]**file.

![](assets/6_4_workstation_groups_4.png)

Här är de mest grundläggande parametrarna som ska läggas till i **[!DNL User List.cfg]**-filen. Medlemmarna kan sedan läggas till i arbetsstationsvyn.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Precis som med alla **[!DNL .cfg]**-filer som du redigerar manuellt måste du använda blanksteg i stället för tabbar och vara noga med att tänka på blanksteg och syntax. Ett fel i den här filen gör att *Adobe Insight Server* ignorerar användarlistfilen.

Fältet **Namn** i varje **Åtkomstgrupp** refereras i filen [!DNL Access Control.cfg].

>[!NOTE]
>
>Endast giltiga medlemmar med katalogtjänstprefix, som **CN:** eller **OU:**, accepteras och de får inte innehålla jokertecken (*).

## Konfigurera filen Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

En administratör aktiverar den här funktionen först genom att öppna filen **[!DNL Components]>[!DNL Communications.cfg]** och lägga till en ny nyckel med namnet **[!DNL Access Control User List File]**. Strängvärdet för den här nyckeln är sökvägen till den nya filen.

1. Klicka på **Komponenter** från serverfilerna och högerklicka på bockmarkeringen i serverkolumnen. Klicka på **Gör lokal**.

   En vit bock visas i kolumnen **Temp**.

1. Högerklicka på bockmarkeringen i kolumnen **Temp** och välj **Öppna** > **i Workstation**.

1. Högerklicka på **komponent** i filen **Communication.cfg** och välj **Lägg till anpassad nyckel.** ![](assets/6_4_workstation_groups.png)

1. Ange **namnet** som *Användarlistfil för åtkomstkontroll* och ställ in **Av typ** som *sträng*.

   >[!NOTE]
   Du kan inte skapa den nya listfilen som en sökväg. För att åtgärda detta måste du spara filen, öppna den i en redigerare (Anteckningar) och ändra String till Path:

   Före:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   Efter:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. Spara **[!DNL Communications.cfg]**-filen och (om det behövs) spara den på servern. Komponenterna i servern startas om för att säkerställa att du inte har gjort några misstag som kan förhindra att **[!DNL Communications.cfg]**-filen tolkas.
1. Om datorn innehåller bearbetningsservrar ändrar du konfigurationsfilen i **[!DNL Components for Processing Servers.cfg]**-filen.
1. Högerklicka på **[!DNL Communications.cfg]** och spara på servern.

Datans Workbench administratör kan nu bekräfta att de avsedda användarna har åtkomst till användarlistfilen och tillåta användarna att hantera gruppen. Användaren/användarna kan öppna användarlistfilen, redigera den och lägga till och ta bort CN- eller OU-medlemmar efter behov.

## Synkronisera filen Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

Administratören kan sedan redigera **[!DNL Access Control.cfg]** och infoga referenser till de grupper som definieras av filen *Användarlista*.

Referenserna till gruppen/grupperna ska infogas precis som alla andra medlemmar, men med följande syntax:

```
$(Group Name)
```

Där &quot;Gruppnamn&quot; matchar det som definieras i användarlistfilen, inklusive blanktecken. ![](assets/6_4_workstation_groups_2.png)

Nu kan Datans Workbench administratör bekräfta att utvalda gruppanvändare har åtkomst till användarlistfilen. De valda användarna kan sedan öppna **[!DNL User List.cfg]**-filen, redigera den och lägga till och ta bort CN- eller OU-medlemmar efter behov.
