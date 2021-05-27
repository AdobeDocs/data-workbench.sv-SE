---
description: Information om hur du konfigurerar klustret på Överordnad Insight Server, uppdaterar åtkomstkontrollsfilen för ett kluster och mycket mer.
title: Konfigurera Överordnad Insight Server for Clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 0%

---

# Konfigurera Överordnad Insight Server för klustring{#configuring-the-master-insight-server-for-clustering}

Information om hur du konfigurerar klustret på Överordnad Insight Server, uppdaterar åtkomstkontrollsfilen för ett kluster och mycket mer.

Konfigurera klustret genom att utföra följande steg på överordnad [!DNL Insight Server]:

* Lägg till de vanliga namnen och adresserna för bearbetningen [!DNL Insight Servers’] i adressfilen.
* Lägg till alla [!DNL Insight Servers] i gruppen Klusterservrar i filen [!DNL Access Control.cfg].

* Uppdatera filen [!DNL Synchronize.cfg] i katalogen Components for Processing Servers så att den pekar på överordnad [!DNL Insight Server].

* Om det behövs ändrar du [!DNL Disk Files.cfg]-filen i katalogen Komponenter för bearbetningsservrar för att ange platsen för [!DNL temp.db]-filen vid bearbetningen [!DNL Insight Servers].

För att kunna utföra dessa steg måste du känna till de vanliga namnen (som anges i de digitala certifikaten för den enskilda [!DNL Insight Server]) och IP-adresserna för varje [!DNL Insight Server] i klustret. Om du inte redan har den här informationen kan du hämta den innan du fortsätter.

>[!NOTE]
>
>Processerna som beskrivs i det här avsnittet kräver [!DNL Insight]. Om du inte har installerat [!DNL Insight] följer du instruktionerna i **[!DNL Insight]användarhandboken** innan du fortsätter.

## Lägger till bearbetningsinsight-servrar till adressfilen {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Använd följande procedur för att lägga till de vanliga namnen och IP-adresserna för bearbetningen [!DNL Insight Servers’] i adressfilen på överordnad [!DNL Insight Server]. (Även om adressfilen underhålls och administreras på överordnad [!DNL Insight Server] används den av alla [!DNL Insight Servers] i klustret.)

>[!NOTE]
>
>Följande förutsätter att adressfilen redan har konfigurerats för överordnad [!DNL Insight Server]. Om du inte redan har lagt till de överordnad IP-adresserna [!DNL Insight Server’s] i adressfilen, slutför du proceduren som beskrivs i [Definiera serverns nätverksplats](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) innan du börjar.

**Lägga till bearbetningen  [!DNL Insight Servers] i adressfilen**

1. Starta [!DNL Insight] och läs in konfigurationsprofilen (om den inte redan är öppen) genom att högerklicka på namnlisten och klicka på **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för överordnad **[!UICONTROL Insight Server]** och klicka på **[!UICONTROL Server Files]**.

1. Öppna katalogen Addresses i [!DNL Server Files Manager] och gör följande för att öppna adressfilen [!DNL Insight Server’s]:

   1. Högerklicka på bockmarkeringen i kolumnen *servernamn* och klicka på **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera innehållet i [!DNL Locations]-strukturen och expandera sedan NetworkLocation 0, Addresses och AddressDefinition.
1. Gör följande för att lägga till en AddressDefinition i NetworkLocation 0 för varje bearbetning [!DNL Insight Server] i klustret:

   1. Högerklicka på **[!UICONTROL AddressDefinition]** och klicka på **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. I parametern Name anger du det vanliga namnet för bearbetningen [!DNL Insight Server’s].
   1. Ange IP-adressen för bearbetning [!DNL Insight Server’s] i parametern Address.

      Du kan använda en asterisk som jokertecken i adressfältet, till exempel 10.10.116.* för att förenkla klustring. Se [Förstå åtkomstnivåer](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      I följande exempel definieras ett kluster som innehåller två [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Om servrarna är anslutna till flera nätverk upprepar du steg 6 för att lägga till bearbetningen [!DNL Insight Servers] i NetworkLocations för dessa nätverk.

   I följande exempel visas ett kluster med fyra [!DNL Insight Servers] som är anslutna till två nätverk (&quot;Corporate Intranet&quot; och &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Uppdaterar åtkomstkontrollsfilen för ett kluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Om du vill använda [!DNL Insight Servers] i ett kluster måste varje [!DNL Insight Server] i klustret (inklusive överordnad [!DNL Insight Server]) tillhöra åtkomstkontrollgruppen Klusterservrar. Klusterservergruppen identifierar de servrar (per IP-adress) som tillåts delta i klustret. Även om den här filen underhålls och administreras på överordnad [!DNL Insight Server] används den av alla [!DNL Insight Servers] i klustret.

**Redigera åtkomstkontrollsfilen**

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för överordnad [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.

1. Öppna katalogen Åtkomstkontroll i [!DNL Server Files Manager].
1. Gör följande för att öppna [!DNL Access Control.cfg]-filen:

   1. Högerklicka på bockmarkeringen i kolumnen *servernamn* och klicka på **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera strukturen Åtkomstkontrollgrupper och expandera sedan AccessGroup (klusterservrar).
1. Gör följande för varje [!DNL Insight Server] i klustret (inklusive överordnad [!DNL Insight Server]):

   1. Högerklicka på **[!UICONTROL Members]** och klicka på **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Ange IP-adressen [!DNL Insight Server’s] (dess numeriska IP-adress, inte namnet). Om [!DNL Insight Servers] är ansluten till flera nätverk ska denna AccessGroup endast innehålla de interna adresser som används för kommunikation mellan servrar i klustret med [!DNL Insight Servers].

      Nedan visas AccessGroup (klusterservrar) för ett kluster med fyra [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Konfigurerar synkroniseringsfilen {#section-d23e751771c84da6bab6a34a8db867bc}

Du kan använda följande procedur för att konfigurera den centrala kopian av [!DNL Synchronize.cfg]-filen. Den centrala kopian av den här filen finns på överordnad [!DNL Insight Server]. Bearbetningen [!DNL Insight Servers] i klustret startar kommunikation med överordnad [!DNL Insight Server] för att hämta en uppdaterad kopia av den här filen.

Filen [!DNL Synchronize.cfg] anger platsen för överordnad [!DNL Insight Server]. Den identifierar också den uppsättning administrativa filer som var och en av bearbetningarna [!DNL Insight Servers] i klustret hämtar från överordnad [!DNL Insight Server]. Bearbetningen [!DNL Insight Servers] hämtar automatiskt dessa filer från överordnad [!DNL Insight Server] när de startas. De hämtar också dynamiskt uppdaterade kopior av dessa filer från överordnad [!DNL Insight Server] när filerna ändras.

>[!NOTE]
>
>Även om du konfigurerar filen [!DNL Synchronize.cfg] på överordnad [!DNL Insight Server], används inte den här filen i själva överordnad [!DNL Insight Server]. Du uppdaterar den här filen på överordnad [!DNL Insight Server] så att den är korrekt konfigurerad när bearbetningen [!DNL Insight Servers] hämtar filen.

**Så här uppdaterar du filen Synchronize.cfg på överordnad[!DNL Insight Server]**

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för överordnad [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager] öppnar du katalogen **[!UICONTROL Components]** for Processing Servers.

1. Öppna [!DNL Synchronize.cfg] genom att göra följande:

   1. Högerklicka på bockmarkeringen i kolumnen *servernamn* och klicka på **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera komponentstrukturen.
1. I parametern Primär klusterserveradress anger du IP-adressen för den överordnad (primära) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Om du vill skapa en logg som spelar in varje gång en synkronisering sker mellan överordnad [!DNL Insight Server] och bearbetningen [!DNL Insight Servers] kontrollerar du att parametern Aktivera synkroniseringslogg är inställd på &quot;true&quot;.

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Konfigurera platsen för datauppsättningen (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Utför följande procedur om du vill att bearbetningen [!DNL Insight Servers] ska behålla [!DNL temp.db] (datauppsättningen) i en katalog eller enhet som inte är standardplatsen eller om du vill distribuera [!DNL temp.db] på flera enheter.

>[!NOTE]
>
>Eftersom bearbetningen [!DNL Insight Servers] alla delar samma [!DNL Disk Files.cfg] måste alla ha stöd för den eller de filplatser som du anger i den här filen. Om du till exempel tilldelar [!DNL temp.db] till E: måste varje bearbetning av [!DNL Insight Server] i klustret ha ett E: kör.

**Så här konfigurerar du platsen för temp.db**

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för överordnad [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.

1. Öppna katalogen **[!UICONTROL Components for Processing Servers]** i [!DNL Server Files Manager].

1. Öppna [!DNL Disk Files.cfg] genom att göra följande:

   1. Högerklicka på bockmarkeringen i kolumnen *servernamn* och klicka på **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i kolumnen [!DNL Temp]och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera DiscSpaceManagerComponent-strukturen och expandera sedan listan Diskfiler.
1. Redigera post 0 om du vill ändra platsen för [!DNL temp.db]-filen.
1. Om du vill distribuera [!DNL temp.db] till flera enheter följer du stegen nedan för att skapa ytterligare en post för varje ytterligare enhet.

   1. Högerklicka på **[!UICONTROL Disk Files]** och klicka på **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. I den nya posten anger du platsen där du vill att [!DNL temp.db] ska skrivas.
   Följande visar [!DNL temp.db] skrivet över fyra enheter.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
