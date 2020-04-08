---
description: Information om hur du konfigurerar klustret på Master Insight Server, uppdaterar åtkomstkontrollsfilen för ett kluster med mera.
solution: Insight
title: Konfigurera Master Insight Server for Clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# Konfigurera Master Insight Server for Clustering{#configuring-the-master-insight-server-for-clustering}

Information om hur du konfigurerar klustret på Master Insight Server, uppdaterar åtkomstkontrollsfilen för ett kluster med mera.

Så här konfigurerar du klustret: [!DNL Insight Server]

* Lägg till de [!DNL Insight Servers’] vanliga namn och adresser som bearbetas i adressfilen.
* Lägg till alla [!DNL Insight Servers] i gruppen Klusterservrar i [!DNL Access Control.cfg] filen.

* Uppdatera [!DNL Synchronize.cfg] filen i katalogen Komponenter för bearbetning av servrar så att den pekar på huvudservern [!DNL Insight Server].

* Om det behövs ändrar du filen i katalogen Komponenter för bearbetning av servrar för att ange platsen för [!DNL Disk Files.cfg] filen som bearbetas [!DNL temp.db] [!DNL Insight Servers].

För att kunna utföra dessa steg måste du känna till de vanliga namnen (som anges i de digitala certifikaten för den enskilda personen [!DNL Insight Server]) och IP-adresserna för varje [!DNL Insight Server] i klustret. Om du inte redan har den här informationen kan du hämta den innan du fortsätter.

>[!NOTE]
>
>De procedurer som beskrivs i detta avsnitt kräver [!DNL Insight]. Om du inte har installerat [!DNL Insight]följer du instruktionerna i **[!DNL Insight]användarhandboken **innan du fortsätter.

## Lägga till bearbetningsinsight-servrar till adressfilen {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Använd följande procedur för att lägga till de [!DNL Insight Servers’] vanliga namn och IP-adresser som bearbetas i adressfilen på huvudservern [!DNL Insight Server]. (Även om adressfilen underhålls och administreras på huvudservern [!DNL Insight Server]används den av alla [!DNL Insight Servers] i klustret.)

>[!NOTE]
>
>Följande förutsätter att adressfilen redan har konfigurerats för huvudservern [!DNL Insight Server]. Om du inte redan har lagt till IP-huvudadressen/huvudadresserna till [!DNL Insight Server’s] adressfilen ska du slutföra proceduren som beskrivs i [Definiera serverns nätverksplats](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) innan du börjar.

**Lägga till bearbetningen[!DNL Insight Servers]i adressfilen**

1. Starta [!DNL Insight] och läs in konfigurationsprofilen (om den inte redan är öppen) genom att högerklicka på namnlisten och klicka på **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.

1. Högerklicka på mallsikonen **[!UICONTROL Insight Server]** och klicka på **[!UICONTROL Server Files]**.

1. Öppna katalogen Addresses i [!DNL Server Files Manager]och gör följande för att öppna [!DNL Insight Server’s] adressfilen:

   1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* och klicka på **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i [!DNL Temp] kolumnen och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera innehållet i [!DNL Locations] strukturen och expandera sedan NetworkLocation 0, Addresses och AddressDefinition.
1. Gör följande för att lägga till en AddressDefinition i NetworkLocation 0 för varje bearbetning [!DNL Insight Server] i klustret:

   1. Högerklicka **[!UICONTROL AddressDefinition]** och klicka **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Ange det [!DNL Insight Server’s] vanliga namnet för bearbetningen i parametern Namn.
   1. Ange den behandlande [!DNL Insight Server’s] IP-adressen i parametern Adress.

      Du kan använda en asterisk som jokertecken i adressfältet, till exempel 10.10.116.* för att förenkla klustring. Se [Åtkomstnivåer](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      I följande exempel definieras ett kluster som innehåller två [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Om servrarna är anslutna till flera nätverk upprepar du steg 6 för att lägga till bearbetningen [!DNL Insight Servers] till NetworkLocations för dessa nätverk.

   I följande exempel visas ett kluster med fyra [!DNL Insight Servers] anslutna nätverk (&quot;Corporate Intranet&quot; och &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Uppdatera åtkomstkontrollsfilen för ett kluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Om du vill använda [!DNL Insight Servers] i ett kluster måste varje [!DNL Insight Server] i klustret (inklusive huvudklustret [!DNL Insight Server]) tillhöra åtkomstkontrollgruppen för klusterservrar. Klusterservergruppen identifierar de servrar (per IP-adress) som tillåts delta i klustret. Även om den här filen underhålls och administreras på huvudservern [!DNL Insight Server]används den av alla [!DNL Insight Servers] i klustret.

**Redigera åtkomstkontrollsfilen**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.

1. Högerklicka på mallsikonen [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.

1. Öppna katalogen Åtkomstkontroll i [!DNL Server Files Manager].
1. Öppna [!DNL Access Control.cfg] filen genom att göra följande:

   1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* och klicka på **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i [!DNL Temp] kolumnen och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera strukturen Åtkomstkontrollgrupper och expandera sedan AccessGroup (klusterservrar).
1. Gör följande för varje [!DNL Insight Server] i klustret (inklusive huvudprogrammet [!DNL Insight Server]):

   1. Högerklicka **[!UICONTROL Members]** och klicka **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Ange [!DNL Insight Server’s] IP-adressen (den numeriska IP-adressen, inte namnet). Om [!DNL Insight Servers] är anslutna till flera nätverk ska denna AccessGroup bara innehålla de interna adresser som [!DNL Insight Servers] används för kommunikation mellan servrar i klustret.

      Nedan visas AccessGroup (klusterservrar) för ett kluster med fyra [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Konfigurera synkroniseringsfilen {#section-d23e751771c84da6bab6a34a8db867bc}

Du kan använda följande procedur för att konfigurera den centrala kopian av [!DNL Synchronize.cfg] filen. Den centrala kopian av den här filen ligger kvar på mallsidan [!DNL Insight Server]. Bearbetningen [!DNL Insight Servers] i klustret initierar kommunikation med huvudservern [!DNL Insight Server] för att hämta en uppdaterad kopia av den här filen.

Filen anger [!DNL Synchronize.cfg] mallens plats [!DNL Insight Server]. Den identifierar också den uppsättning administrativa filer som varje bearbetning [!DNL Insight Servers] i klustret hämtar från huvudservern [!DNL Insight Server]. Bearbetningen hämtar [!DNL Insight Servers] automatiskt dessa filer från mallsidan [!DNL Insight Server] när de startas. De hämtar också dynamiskt uppdaterade kopior av dessa filer från mallsidan [!DNL Insight Server] när filerna ändras.

>[!NOTE]
>
>Även om du konfigurerar [!DNL Synchronize.cfg] filen på mallsidan [!DNL Insight Server]använder mallsidan [!DNL Insight Server] inte den här filen. Du uppdaterar den här filen på mallsidan [!DNL Insight Server] så att den är korrekt konfigurerad när bearbetningen [!DNL Insight Servers] hämtar filen.

**Så här uppdaterar du filen Synchronize.cfg på mallsidan[!DNL Insight Server]**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.

1. Högerklicka på mallsikonen [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.

1. Öppna [!DNL Server Files Manager]katalogen **[!UICONTROL Components]** för att bearbeta servrar i .

1. Öppna [!DNL Synchronize.cfg]genom att göra följande:

   1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* och klicka på **[!UICONTROL Make Local]**.

   1. Högerklicka på [!DNL Temp] bockmarkeringen och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera komponentstrukturen.
1. I parametern Primär klusterserveradress anger du huvudserverns IP-adress (primär) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Om du vill skapa en logg som registreras varje gång synkroniseringen sker mellan huvudservern [!DNL Insight Server] och bearbetningen [!DNL Insight Servers]kontrollerar du att parametern Aktivera synkroniseringslogg är inställd på &quot;true&quot;.

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Konfigurera platsen för datauppsättningen (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Utför följande procedur om du vill att bearbetningen [!DNL Insight Servers] ska underhålla [!DNL temp.db] (datauppsättningen) i en annan katalog eller enhet än standardplatsen eller om du vill distribuera [!DNL temp.db] över flera enheter.

>[!NOTE]
>
>Eftersom bearbetningen [!DNL Insight Servers] alla delar samma [!DNL Disk Files.cfg]måste alla ha stöd för den eller de filplatser som du anger i den här filen. Om du till exempel tilldelar [!DNL temp.db] till E: måste varje bearbetning [!DNL Insight Server] i klustret ha ett E: kör.

**Så här konfigurerar du platsen för temp.db**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.

1. Högerklicka på mallsikonen [!DNL Insight Server] och klicka på **[!UICONTROL Server Files]**.

1. Öppna [!DNL Server Files Manager]katalogen i **[!UICONTROL Components for Processing Servers]** .

1. Öppna [!DNL Disk Files.cfg]genom att göra följande:

   1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* och klicka på **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i [!DNL Temp]kolumnen och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera DiscSpaceManagerComponent-strukturen och expandera sedan listan Diskfiler.
1. Redigera post 0 om du vill ändra platsen för [!DNL temp.db] filen.
1. Om du vill distribuera [!DNL temp.db] till flera enheter följer du stegen nedan för att skapa ytterligare en post för varje ytterligare enhet.

   1. Högerklicka **[!UICONTROL Disk Files]** och klicka **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. I den nya posten anger du platsen där du vill [!DNL temp.db] skriva.
   Följande visar [!DNL temp.db] skrivna över fyra enheter.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

