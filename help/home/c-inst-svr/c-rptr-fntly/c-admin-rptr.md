---
description: De administrativa uppgifterna för repetitiva funktioner liknar dem för Insight Server.
solution: Analytics
title: Administrera upprepare
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---


# Administrera upprepare{#administering-repeater}

De administrativa uppgifterna för repetitiva funktioner liknar dem för Insight Server.

Följande administrativa uppgifter är tillämpliga: undantag eller ändringar som du måste göra så att [!DNL Insight Server] DPU:n kan användas med den upprepade servern noteras efter varje steg.

* [Validera det digitala certifikatet igen](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Kontrollera att tjänsten körs](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) i listan över tjänster på kontrollpanelen Tjänster och sök efter&quot;Upprepare&quot;.

* [Konfigurera åtkomstkontroll](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Övervaka diskutrymme](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) De datatyper som gäller för den upprepade servern är händelser, operativsystem och systemdata. Om du använder den upprepade servern för lagring av säkerhetskopior och det blir nödvändigt att göra mer datalagringsutrymme tillgängligt på datorn, kan du flytta alla loggfiler utom den senaste dagens till en annan dator eller ett annat datalagringsmedium (zip-enhet, band osv.). Om du flyttar data behöver du inte stoppa repetitionstjänsten.

   >[!NOTE]
   >
   >Du bör kontrollera integriteten hos säkerhetskopiorna av dina [!DNL .vsl] filer innan du tar bort någon av dem från Repeater.

* [Konfigurera administrativa aviseringar](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Övervaka administrativa händelser](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Övervaka granskningsloggar](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Konfigurera kommunikation](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Omstart av tjänstens](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74) funktionalitet [!DNL Repeater] är utformad för att köras kontinuerligt. Om du startar om datorn startar uppreparen om automatiskt. Om du behöver starta och sluta upprepa manuellt kan du göra det med hjälp av kontrollpanelen Tjänster i Windows.

