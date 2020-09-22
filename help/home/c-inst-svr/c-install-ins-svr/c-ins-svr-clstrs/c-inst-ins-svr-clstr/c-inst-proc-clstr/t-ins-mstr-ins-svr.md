---
description: Om du vill använda ett kluster måste du utse en Insight-server i klustret till överordnad Insight Server.
solution: Analytics
title: Installera Överordnad Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---


# Installera Överordnad Insight Server{#installing-the-master-insight-server}

Om du vill använda ett kluster måste du utse en Insight-server i klustret till överordnad Insight Server.

En klientkomponent som [!DNL Insight] eller [!DNL Report] ansluter till överordnad [!DNL Insight Server] i början av en session. Vid efterföljande punkter under sessionen kan klienten ansluta till andra [!DNL Insight Servers] i klustret för att utföra en fråga. De efterföljande anslutningarna mellan klienten och den andra [!DNL Insight Servers] i klustret förmedlas av överordnad [!DNL Insight Server] och är genomskinliga för klienten.

Förutom att förmedla anslutningar mellan en klient och andra [!DNL Insight Servers] i klustret fungerar överordnad [!DNL Insight Server] som den centrala administrativa punkten i hela klustret. När du administrerar ett kluster uppdaterar du det överordnad [!DNL Insight Server]. De administrativa ändringar du gör på överordnad [!DNL Insight Server] hämtas av den andra [!DNL Insight Servers] i klustret.

**Installera överordnad[!DNL Insight Server]**

1. Bestäm vilken dator som ska fungera som överordnad [!DNL Insight Server].
1. Installera och konfigurera [!DNL Insight Server] (vanligtvis en [!DNL Insight Server] FSU) på den här datorn enligt beskrivningen i [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installera [!DNL Insight] och konfigurera en anslutning till överordnad [!DNL Insight Server] enligt beskrivningen i *[!DNL Insight]användarhandboken*.
