---
description: Administratörer kan ge arbetsstationsanvändare delvis möjlighet att hantera åtkomstkontroll för anpassade grupper.
title: Användaradministration för gruppmedlemsåtkomst
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 0%

---

# Användaradministration för gruppmedlemsåtkomst{#user-administration-of-group-member-access}

{{eol}}

Administratörer kan ge arbetsstationsanvändare delvis möjlighet att hantera åtkomstkontroll för anpassade grupper.

**Självadministration av gruppmedlemmens åtkomst** ger rättigheter till icke-administratörer att lägga till och ta bort medlemmar i en anpassad grupp. Administratören skapar en **Användarlista** och ställer in gruppåtkomst i [Åtkomstkontroll.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) för de nya gruppmedlemmarna.

**Åtkomst till serverhanteraren**

Konfigurera **[!DNL User List]** -filen och synkronisera den med **[!DNL Communications.cfg]** filen görs i **Serverhanteraren** arbetsyta.

1. Klicka på **Administratör** tab > **Datauppsättning och profil** -fliken.

1. Öppna **Serverhanteraren** arbetsyta.
1. Högerklicka >*ditt servernamn*> i diagrammet och välj **Filer**.

   Serverfilerna öppnas i en tabell med kolumner *Fil*, *`<server name>`* och *Tillfällig*.

1. **Gör lokal** genom att högerklicka i serverkolumnen för en serverfil (för den här funktionen) **[!DNL Access Control]** och **[!DNL Components/Communications.cfg)]**.

   En vit bock visas i dialogrutan **Tillfällig** kolumn. Du kan redigera i mappen Temp. Högerklicka sedan på bockmarkeringen och **Spara i** servern. (Den blir röd när den synkroniseras med servern).

## Skapa filen User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

Administratören måste skapa en **[!DNL User List.cfg]** i **[!DNL Access Control]** mapp.

1. Högerklicka** på raden Åtkomstkontroll** i **Tillfällig** kolumn och markera **Öppna** > **Mapp**. ![](assets/6_4_workstation_groups_3.png)

   Åtkomstkontrollmappen i **Tillfällig** kommer att öppnas med en lista över **[!DNL Access Control.cfg]** -fil.

1. Lägg till ytterligare en textfil i den här mappen och ge den ett namn **[!DNL User List.cfg]** (bredvid **[!DNL Access Control.cfg]**).

1. Lägg till följande parametrar i **[!DNL User List.cfg]** -fil.

Användarlistfilen ska innehålla en vektor med **AccessGroup** objekt, och **AccessGroup** objektet ska ha ett namn och en vektor med strängar som kallas **Medlemmar**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Du kan sedan redigera och lägga till användare i arbetsstationsvyn i **[!DNL User List.cfg]**fil.

![](assets/6_4_workstation_groups_4.png)

Här är de mest grundläggande parametrarna att lägga till i **[!DNL User List.cfg]** -fil. Medlemmarna kan sedan läggas till i arbetsstationsvyn.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Som med alla **[!DNL .cfg]** filen som du redigerar manuellt måste du se till att använda blanksteg i stället för tabbar och vara noga med att tänka på blanksteg och syntax. Ett fel i den här filen orsakar *Adobe Insight Server* om du vill ignorera filen med användarlistan.

The **Namn** fält i varje **Åtkomstgrupp** kommer att refereras i [!DNL Access Control.cfg] -fil.

>[!NOTE]
>
>Endast giltiga medlemmar med katalogtjänstprefix, som **CN:** eller **OU:** accepteras och de får inte innehålla jokertecken (&#42;).

## Konfigurera filen Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

En administratör aktiverar den här funktionen först genom att öppna **[!DNL Components]>[!DNL Communications.cfg]** och lägga till en ny nyckel med namnet **[!DNL Access Control User List File]**. Strängvärdet för den här nyckeln är sökvägen till den nya filen.

1. Från serverfilerna klickar du på **Komponenter** och högerklicka på bockmarkeringen i serverkolumnen. Klicka **Gör lokal**.

   En vit bock visas i dialogrutan **Tillfällig** kolumn.

1. Högerklicka på bockmarkeringen i dialogrutan **Tillfällig** kolumn och markera **Öppna** > **i Workstation**.

1. I **Communication.cfg** fil, högerklicka **komponent** och markera **Lägg till anpassad nyckel.** ![](assets/6_4_workstation_groups.png)

1. Skriv **Namn** as *Användarlistfil för åtkomstkontroll* och ange **Av typ** as *Sträng*.

   >[!NOTE]
   >
   >Du kan inte skapa den nya listfilen som en sökväg. För att åtgärda detta måste du spara filen, öppna den i en redigerare (Anteckningar) och ändra String till Path:

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

1. Spara **[!DNL Communications.cfg]** och (om det behövs) spara den på servern. Detta startar om komponenterna på servern för att säkerställa att du inte har gjort några misstag som kan förhindra **[!DNL Communications.cfg]** från att analyseras.
1. Om ditt system innehåller bearbetningsservrar ändrar du konfigurationsfilen i **[!DNL Components for Processing Servers.cfg]** -fil.
1. Högerklicka **[!DNL Communications.cfg]** och spara på servern.

Datans Workbench administratör kan nu bekräfta att de avsedda användarna har åtkomst till användarlistfilen och tillåta användarna att hantera gruppen. Användaren/användarna kan öppna användarlistfilen, redigera den och lägga till och ta bort CN- eller OU-medlemmar efter behov.

## Synkronisera filen Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

Administratören kan sedan redigera **[!DNL Access Control.cfg]** och infoga referenser till de grupper som definieras av *Användarlista* -fil.

Referenserna till gruppen/grupperna ska infogas precis som alla andra medlemmar, men med följande syntax:

```
$(Group Name)
```

Där &quot;Gruppnamn&quot; matchar det som definieras i användarlistfilen, inklusive blanktecken. ![](assets/6_4_workstation_groups_2.png)

Nu kan Datans Workbench administratör bekräfta att utvalda gruppanvändare har åtkomst till användarlistfilen. Användarna kan sedan öppna **[!DNL User List.cfg]** filma, redigera och lägg till och ta bort CN- eller OU-medlemmar efter behov.
