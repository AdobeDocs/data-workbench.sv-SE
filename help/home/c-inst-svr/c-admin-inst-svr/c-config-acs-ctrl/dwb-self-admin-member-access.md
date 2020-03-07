---
description: Administratörer kan ge arbetsstationsanvändare delvis möjlighet att hantera åtkomstkontroll för anpassade grupper.
title: Användaradministration för gruppmedlemsåtkomst
uuid: c31128f9-1094-4337-9bf6-96401278df33
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Användaradministration för gruppmedlemsåtkomst{#user-administration-of-group-member-access}

Administratörer kan ge arbetsstationsanvändare delvis möjlighet att hantera åtkomstkontroll för anpassade grupper.

**Självadministration av gruppmedlemsåtkomst** ger rättigheter till icke-administratörer att lägga till och ta bort medlemmar i en anpassad grupp. Administratören skapar en **användarlistfil** och ställer in gruppåtkomst i [Access Control.cfg](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) -filen för de nya gruppmedlemmarna.

**Åtkomst till Serverhanteraren**

Du konfigurerar **[!DNL User List]** filen och synkroniserar den med **[!DNL Communications.cfg]** filen på arbetsytan i **Serverhanteraren** .

1. Klicka på fliken **Admin** > **Datauppsättning och Profil** på skrivbordet.

1. Öppna arbetsytan **Serverhanteraren** .
1. Högerklicka >*ditt servernamn*> i diagrammet och välj **Filer**.

   Serverfilerna öppnas i en tabell med kolumnerna *Arkiv*, *`<server name>`* och *Tillfällig*.

1. **Gör lokal** genom att högerklicka i serverkolumnen för en serverfil (för den här funktionen **[!DNL Access Control]** och **[!DNL Components/Communications.cfg)]**.

   En vit bock visas i kolumnen **Tillfällig** . Du kan redigera i mappen Temp. Högerklicka sedan på bockmarkeringen och **Spara till** servern. (Den blir röd när den synkroniseras med servern).

## Skapa filen User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

Administratören måste skapa en **[!DNL User List.cfg]** fil i **[!DNL Access Control]** mappen.

1. Högerklicka** Åtkomstkontroll** i kolumnen **Tillfällig** och välj **Öppna** > **Mapp**. ![](assets/6_4_workstation_groups_3.png)

   Mappen Åtkomstkontroll i mappen **Temp** öppnas och visar en lista över en enda **[!DNL Access Control.cfg]** fil.

1. Lägg till ytterligare en textfil i den här mappen och ge den ett namn **[!DNL User List.cfg]** (bredvid **[!DNL Access Control.cfg]**).

1. Lägg till följande parametrar i **[!DNL User List.cfg]** filen.

Användarlistfilen ska innehålla en vektor med **AccessGroup** -objekt och varje **AccessGroup** -objekt ska ha ett namn och en vektor med strängar som kallas **medlemmar**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Du kan sedan redigera och lägga till användare i arbetsstationsvyn i **[!DNL User List.cfg]**filen.

![](assets/6_4_workstation_groups_4.png)

Här är de mest grundläggande parametrarna att lägga till i **[!DNL User List.cfg]** filen. Medlemmarna kan sedan läggas till i arbetsstationsvyn.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Precis som för andra **[!DNL .cfg]** filer som du redigerar manuellt bör du se till att använda blanksteg i stället för tabbar och vara noga med att tänka på blanksteg och syntax. Ett fel i den här filen gör att *Adobe Insight Server* ignorerar användarlistfilen.

Fältet **Namn** i varje **åtkomstgrupp** kommer att refereras till i [!DNL Access Control.cfg] filen.

>[!NOTE]
>
>Endast giltiga medlemmar med katalogtjänstprefix, som **CN:** eller **OU:** accepteras och får inte innehålla jokertecken (*).

## Konfigurera filen Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

En administratör aktiverar först den här funktionen genom att öppna **[!DNL Components]>-[!DNL Communications.cfg]**filen och lägga till en ny nyckel med namnet **[!DNL Access Control User List File]**. Strängvärdet för den här nyckeln är sökvägen till den nya filen.

1. Klicka på **Komponenter** i serverfilerna och högerklicka på bockmarkeringen i serverkolumnen. Klicka på **Gör lokal**.

   En vit bock visas i kolumnen **Tillfällig** .

1. Högerklicka på bockmarkeringen i kolumnen **Tillfällig** och välj **Öppna** > **i arbetsstation**.

1. Högerklicka på **komponenten** i filen **Communication.cfg** och välj **Lägg till anpassad nyckel.** ![](assets/6_4_workstation_groups.png)

1. Skriv **namnet** som *åtkomstkontrollens användarlistfil* och ange **typen** som *sträng*.

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

1. Spara **[!DNL Communications.cfg]** filen och (om det behövs) spara den på servern. Komponenterna i servern startas om för att säkerställa att du inte har gjort några misstag som kan förhindra att **[!DNL Communications.cfg]** filen tolkas.
1. Om datorn innehåller bearbetningsservrar ändrar du konfigurationsfilen i **[!DNL Components for Processing Servers.cfg]** filen.
1. Högerklicka **[!DNL Communications.cfg]** och spara på servern.

Data Workbench-administratören kan nu bekräfta att de avsedda användarna har åtkomst till användarlistfilen och tillåta användarna att hantera gruppen. Användaren/användarna kan öppna användarlistfilen, redigera den och lägga till och ta bort CN- eller OU-medlemmar efter behov.

## Synkronisera filen Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

Administratören kan sedan redigera **[!DNL Access Control.cfg]** och infoga referenser till de grupper som definieras av *användarlistfilen* .

Referenserna till gruppen/grupperna ska infogas precis som alla andra medlemmar, men med följande syntax:

```
$(Group Name)
```

Där &quot;Gruppnamn&quot; matchar det som definieras i användarlistfilen, inklusive blanktecken. ![](assets/6_4_workstation_groups_2.png)

Nu kan Data Workbench-administratören bekräfta att utvalda gruppanvändare har åtkomst till användarlistfilen. De valda användarna kan sedan öppna **[!DNL User List.cfg]** filen, redigera den och lägga till och ta bort CN- eller OU-medlemmar efter behov.
