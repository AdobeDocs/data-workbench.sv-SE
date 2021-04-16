---
description: Du kanske vill lägga till en Insight Server FSU i ett befintligt kluster om du vill lagra källdata på ytterligare en filserver eller om du vill konfigurera en säkerhetskopia för din överordnad Insight Server.
title: Lägga till en Insight Server FSU i ett befintligt kluster
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 0%

---

# Lägga till en Insight Server FSU i ett befintligt kluster{#adding-an-insight-server-fsu-to-an-existing-cluster}

Du kanske vill lägga till en Insight Server FSU i ett befintligt kluster om du vill lagra källdata på ytterligare en filserver eller om du vill konfigurera en säkerhetskopia för din överordnad Insight Server.

Om du vill lägga till en FSU på [!DNL Insight Server] i ett befintligt kluster måste du utföra följande procedurer:

1. [Uppdaterar konfigurationsfilerna på den Överordnad servern](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Installera nya Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Konfigurera nya Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Konfigurationsfilerna uppdateras på den Överordnad servern {#section-b5f21f2edb35493da4475de2cdeefca1}

I [!DNL Insight] öppnar du [!DNL Server Files Manager] för din överordnad [!DNL Insight Server] (vanligtvis en [!DNL Insight Server] FSU) och gör följande för varje FSU som du vill lägga till i klustret:

1. Redigera adressfilen på överordnad [!DNL Insight Server] för att inkludera namn och adress för den nya FSU:n enligt beskrivningen i [Lägga till bearbetningsinsiktsservrar i adressfilen](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Lägg till namn och adress för den nya FSU:n i den grupp där klustrets aktuella [!DNL Insight Servers] listas.

1. Redigera åtkomstkontrollsfilen på överordnad [!DNL Insight Server] så att den innehåller IP-adressen för den nya FSU:n enligt beskrivningen i [Uppdatera åtkomstkontrollsfilen för ett kluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installerar den nya Insight Server FSU {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. Gör en zip-fil av installationskatalogen [!DNL Insight Server] på din nuvarande FSU och kopiera filen till den nya FSU:n.
1. Zippa upp filen där du vill placera [!DNL Insight Server]-programvaran.
1. Hämta och installera det digitala certifikatet för den nya FSU:n enligt beskrivningen i [Hämta och installera de digitala certifikaten](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Ange parametrar för minnesanvändning i Windows på den nya FSU:n.
1. Ändra namnet på [!DNL .address]-filen så att det motsvarar namnet på FSU:n enligt beskrivningen i [Definiera serverns nätverksplats](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. Om enhetsstrukturen på den nya FSU:n skiljer sig från den på den primära FSU:n måste du redigera filen [!DNL Disk Files.cfg].

   1. Öppna filen [!DNL Disk Files.cfg] på den nya FSU:n.
   1. Uppdatera inställningarna så att de matchar enheterna i den primära FSU:n enligt beskrivningen i [Övervaka datauppsättningsdataområde](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Spara filen lokalt och på servern.

1. Registrera [!DNL Insight Server] som en Windows-tjänst på den nya FSU-datorn enligt beskrivningen i [Registrera Insight Server som en Windows-tjänst](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Upprepa steg 1 till 6 för varje ytterligare FSU som du lägger till i klustret.

## Konfigurera nya Insight Server FSU {#section-c39334c5bd754d5b98d41ad094333108}

Följande procedurer innehåller instruktioner för specifika konfigurationsuppgifter. Följ de anvisningar som är lämpliga för din implementering av den nya FSU:n.

**Konfigurera FSU för källdatalagring**

Om den nya FSU:n lagrar ytterligare källdata för den datauppsättning som körs i klustret, måste du slutföra filserverns konfigurationsprocess enligt beskrivningen i Konfigurera en [!DNL Insight Server] filserverenhet i kapitlet Loggbehandlingskonfigurationsfil i *Konfigurationshandboken för datauppsättningar*.

**Säkerhetskopiera den överordnad  [!DNL Insight Server] FSU:n till den nya FSU:n**

Om du vill göra den nya FSU-enheten till en säkerhetskopia för överordnad [!DNL Insight Server] (som fungerar som FSU för klustret) måste du ändra synkroniseringsfilen på den nya (säkerhetskopierade) FSU:n så att den synkroniseras med den överordnad FSU:n.

1. På säkerhetskopian [!DNL Insight Server] FSU använder du [!DNL Server Files Manager] för att kopiera filen [!DNL Synchronize.cfg] i mappen [!DNL Components for Processing Servers] till mappen [!DNL Components].

1. Öppna filen [!DNL Synchronize.cfg] (i mappen [!DNL Components]) i [!DNL Insight].

1. Hitta SynchronizeDir som anger platsen för komponentkatalogen. Det kan finnas flera synkroniseringskataloger under Kataloger, så du kan behöva visa innehållet för många av dem (genom att klicka på servernumret) för att hitta önskad server).
1. Redigera SynchronizeDir-posten och lägg till en andra SynchronizeDir-post enligt exemplet nedan.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Spara den ändrade filen med ett nytt namn, till exempel [!DNL FSU_Synchronize.cfg], så att den inte förväxlas med [!DNL Synchronize.cfg]-filerna på DPU:erna i klustret.

1. Använd [!DNL Server Files Manager] för att spara den lokala kopian av den namnändrade filen på servern. Säkerhetskopians FSU hämtar filerna i de identifierade katalogerna från den överordnad FSU:n [!DNL Insight Server] och hämtar dynamiskt uppdaterade kopior av dessa filer från den överordnad FSU:n [!DNL Insight Server] när de ändras.
