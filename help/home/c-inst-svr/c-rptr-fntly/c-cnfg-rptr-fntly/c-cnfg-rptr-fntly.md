---
description: Repeater-funktionaliteten gör att en Insight Server FSU kan ta emot händelsedata från en eller flera källor och replikera data till en eller flera Insight Server FSU:er som kör Insight ServerReplication Service.
title: Konfigurera Repeater-funktioner
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Konfigurera Repeater-funktioner{#configuring-repeater-functionality}

Repeater-funktionaliteten gör att en Insight Server FSU kan ta emot händelsedata från en eller flera källor och replikera data till en eller flera Insight Server FSU:er som kör Insight ServerReplication Service.

Se [Tjänsten Insight Server Replication](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). Den här funktionen möjliggör datareplikering till redundanta anläggningar för katastrofåterställning. Målservrarna fungerar som nätverksklienter och ansluter till käll-FSU:n för att begära kopior av händelsedata som ska ingå i flera datauppsättningar.

Du kan använda upprepningsfunktioner i nätverksinfrastrukturer med flera lager av brandväggar för att få kommunikation mellan komponenter som avgränsas av brandväggar med en port och en port.

Mer information om systemkraven för installation, konfigurering och drift [!DNL Repeater] finns i dokumentet *Minimum System Requirements*.

Om du vill installera [!DNL Repeater] måste du utföra följande två procedurer:

* [Konfigurera en Insight Server FSU för Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [Konfigurera åtkomstkontroll för måldatorer](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

Om nätverkets brandväggar tillåter åtkomst till din [!DNL Repeater] från [!DNL Insight] kan du skapa en anslutning enligt beskrivningen i [Skapa en anslutning mellan Insight och Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
