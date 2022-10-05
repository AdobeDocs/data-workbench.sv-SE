---
description: Information om hur du konfigurerar klustret på Överordnad Insight Server, uppdaterar åtkomstkontrollsfilen för ett kluster och mycket mer.
title: Konfigurera Överordnad Insight Server for Clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 0%

---

# Konfigurera Överordnad Insight Server for Clustering{#configuring-the-master-insight-server-for-clustering}

{{eol}}

Information om hur du konfigurerar klustret på Överordnad Insight Server, uppdaterar åtkomstkontrollsfilen för ett kluster och mycket mer.

Konfigurera klustret genom att utföra följande steg på överordnad [!DNL Insight Server]:

* Lägg till bearbetningen [!DNL Insight Servers’] vanliga namn och adresser till adressfilen.
* Lägg till alla [!DNL Insight Servers] till gruppen Klusterservrar i [!DNL Access Control.cfg] -fil.

* Uppdatera [!DNL Synchronize.cfg] i katalogen Components for Processing Servers så att den pekar på överordnad [!DNL Insight Server].

* Ändra [!DNL Disk Files.cfg] i katalogen Komponenter för bearbetning av servrar för att ange platsen för [!DNL temp.db] fil som bearbetas [!DNL Insight Servers].

För att kunna utföra dessa steg måste du känna till de vanliga namnen (som anges i de digitala certifikaten för den enskilda personen) [!DNL Insight Server]) och IP-adresserna för varje [!DNL Insight Server] i klustret. Om du inte redan har den här informationen kan du hämta den innan du fortsätter.

>[!NOTE]
>
>Processerna som beskrivs i detta avsnitt kräver [!DNL Insight]. Om du inte har installerat [!DNL Insight]följer du instruktionerna i **[!DNL Insight]Användarhandbok** innan du fortsätter.

## Lägga till bearbetningsinsight-servrar till adressfilen {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Använd följande procedur för att lägga till bearbetningen [!DNL Insight Servers’] vanliga namn och IP-adresser till adressfilen på överordnad [!DNL Insight Server]. (Även om adressfilen underhålls och administreras på överordnad [!DNL Insight Server]används den av alla [!DNL Insight Servers] i klustret.)

>[!NOTE]
>
>Följande förutsätter att adressfilen redan har konfigurerats för överordnad [!DNL Insight Server]. Om du inte redan har lagt till överordnad [!DNL Insight Server’s] IP-adress(er) till adressfilen, utför den procedur som beskrivs i [Definiera serverns nätverksplats](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) innan du börjar.

**Lägga till bearbetningen [!DNL Insight Servers] till adressfilen**

1. Starta [!DNL Insight] och läsa in konfigurationsprofilen (om den inte redan är öppen) genom att högerklicka på namnlisten och klicka på **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för överordnad **[!UICONTROL Insight Server]** och klicka **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager]öppnar du katalogen Addresses och gör följande för att öppna [!DNL Insight Server’s] adressfil:

   1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn och klicka **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera innehållet i [!DNL Locations] struktur och sedan expandera NetworkLocation 0, Addresses och AddressDefinition.
1. Gör följande för att lägga till en AddressDefinition i NetworkLocation 0 för varje bearbetning [!DNL Insight Server] i klustret:

   1. Högerklicka **[!UICONTROL AddressDefinition]** och klicka **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. I parametern Namn anger du bearbetningen [!DNL Insight Server’s] eget namn.
   1. I parametern Address anger du bearbetningen [!DNL Insight Server’s] IP-adress.

      Du kan använda en asterisk som jokertecken i adressfältet, till exempel 10.10.116.&#42;, för att förenkla klustring. Se [Om åtkomstnivåer](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      I följande exempel definieras ett kluster som innehåller två [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Om servrarna är anslutna till flera nätverk upprepar du steg 6 för att lägga till bearbetningen [!DNL Insight Servers] till NetworkLocations för dessa nätverk.

   I följande exempel visas ett kluster med fyra [!DNL Insight Servers] kopplade till två nätverk (&quot;Corporate Intranet&quot; och&quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL Temp] kolumn och markera **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Uppdatera åtkomstkontrollsfilen för ett kluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Används [!DNL Insight Servers] i ett kluster, var och en [!DNL Insight Server] i klustret (inklusive överordnad [!DNL Insight Server]) måste tillhöra åtkomstkontrollgruppen Klusterservrar. Klusterservergruppen identifierar de servrar (per IP-adress) som tillåts delta i klustret. Även om den här filen bevaras och administreras på överordnad [!DNL Insight Server]används den av alla [!DNL Insight Servers] i klustret.

**Redigera åtkomstkontrollsfilen**

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för överordnad [!DNL Insight Server] och klicka **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager]öppnar du katalogen Åtkomstkontroll.
1. Gör följande för att öppna [!DNL Access Control.cfg] fil:

   1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn och klicka **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera strukturen Åtkomstkontrollgrupper och expandera sedan AccessGroup (klusterservrar).
1. För varje [!DNL Insight Server] i klustret (inklusive överordnad [!DNL Insight Server]) gör du följande:

   1. Högerklicka **[!UICONTROL Members]** och klicka **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Ange [!DNL Insight Server’s] IP-adress (dess numeriska IP-adress, inte dess namn). Om [!DNL Insight Servers] är anslutna till flera nätverk, ska denna AccessGroup endast innehålla de interna adresserna som [!DNL Insight Servers] används för kommunikation mellan servrar i klustret.

      Nedan visas AccessGroup (klusterservrar) för ett kluster med fyra [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Konfigurera synkroniseringsfilen {#section-d23e751771c84da6bab6a34a8db867bc}

Du kan använda följande procedur för att konfigurera den centrala kopian av [!DNL Synchronize.cfg] -fil. Den centrala kopian av filen finns på överordnad [!DNL Insight Server]. Bearbetningen [!DNL Insight Servers] i klustret initierar kommunikation med överordnad [!DNL Insight Server] om du vill hämta en uppdaterad kopia av den här filen.

The [!DNL Synchronize.cfg] anger platsen för den överordnad [!DNL Insight Server]. Den identifierar också den uppsättning administrativa filer som bearbetningen omfattar [!DNL Insight Servers] i klustret hämtar från överordnad [!DNL Insight Server]. Bearbetningen [!DNL Insight Servers] automatiskt hämta dessa filer från överordnad [!DNL Insight Server] när de börjar. De hämtar även dynamiskt uppdaterade kopior av dessa filer från överordnad [!DNL Insight Server] när filerna ändras.

>[!NOTE]
>
>Även om du konfigurerar [!DNL Synchronize.cfg] filen på överordnad [!DNL Insight Server], den överordnad [!DNL Insight Server] använder inte den här filen. Du uppdaterar den här filen på överordnad [!DNL Insight Server] så att den är korrekt konfigurerad när bearbetningen [!DNL Insight Servers] hämta filen.

**Så här uppdaterar du filen Synchronize.cfg på överordnad[!DNL Insight Server]**

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för överordnad [!DNL Insight Server] och klicka **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager]öppnar du **[!UICONTROL Components]** för att bearbeta serverkatalogen.

1. Öppna följande [!DNL Synchronize.cfg]:

   1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn och klicka **[!UICONTROL Make Local]**.

   1. Högerklicka på [!DNL Temp] markera och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera komponentstrukturen.
1. Ange IP-adressen för överordnad (primär) i parametern Klustrets primära serveradress. **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Skapa en logg som spelar in varje gång synkronisering sker mellan överordnad [!DNL Insight Server] och bearbetningen [!DNL Insight Servers]Kontrollera att parametern Enable Synchronization Log är inställd på &quot;true&quot;.

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Konfigurera platsen för datauppsättningen (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Utför följande procedur om du vill bearbeta [!DNL Insight Servers] att behålla [!DNL temp.db] (datauppsättningen) i en annan katalog eller enhet än standardplatsen eller om du vill distribuera [!DNL temp.db] över flera enheter.

>[!NOTE]
>
>Eftersom bearbetningen [!DNL Insight Servers] alla delar samma [!DNL Disk Files.cfg]måste alla ha stöd för den eller de filplatser som du anger i den här filen. Om du till exempel tilldelar [!DNL temp.db] till E: enhet, varje bearbetning [!DNL Insight Server] i klustret måste ha ett E: kör.

**Så här konfigurerar du platsen för temp.db**

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för överordnad [!DNL Insight Server] och klicka **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager]öppnar du **[!UICONTROL Components for Processing Servers]** katalog.

1. Öppna följande [!DNL Disk Files.cfg]:

   1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn och klicka **[!UICONTROL Make Local]**.

   1. Högerklicka på bockmarkeringen i dialogrutan [!DNL Temp]kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expandera DiscSpaceManagerComponent-strukturen och expandera sedan listan Diskfiler.
1. Redigera post 0 om du vill ändra platsen för [!DNL temp.db] -fil.
1. Om du vill distribuera [!DNL temp.db] på flera enheter, använd stegen nedan för att skapa ytterligare en post för varje ytterligare enhet.

   1. Högerklicka **[!UICONTROL Disk Files]** och klicka **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. I den nya posten anger du platsen där du vill ha den [!DNL temp.db] skriven.
   Följande exempel [!DNL temp.db] skrivna över fyra enheter.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
