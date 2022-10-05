---
description: Om du vill använda ett kluster måste du utse en Insight-server i klustret till överordnad Insight Server.
title: Installera Överordnad Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# Installera Överordnad Insight Server{#installing-the-master-insight-server}

{{eol}}

Om du vill använda ett kluster måste du utse en Insight-server i klustret till överordnad Insight Server.

En klientkomponent som [!DNL Insight] eller [!DNL Report] ansluter till överordnad [!DNL Insight Server] i början av en session. Vid efterföljande punkter under sessionen kan klienten ansluta till andra [!DNL Insight Servers] i klustret för att utföra en fråga. Dessa efterföljande anslutningar mellan klienten och den andra [!DNL Insight Servers] i klustret förmedlas av överordnad [!DNL Insight Server] och är genomskinliga för kunden.

Förutom att förmedla anslutningar mellan en klient och andra [!DNL Insight Servers] i klustret, den överordnad [!DNL Insight Server] fungerar som central administrativ punkt för hela klustret. När du administrerar ett kluster uppdaterar du den överordnad [!DNL Insight Server]. De administrativa ändringar du gör på överordnad [!DNL Insight Server] hämtas av den andra [!DNL Insight Servers] i klustret.

**Installera överordnad[!DNL Insight Server]**

1. Bestäm vilken dator som ska fungera som överordnad [!DNL Insight Server].
1. Installera och konfigurera [!DNL Insight Server] (vanligtvis en [!DNL Insight Server] FSU) på den här datorn enligt beskrivningen i [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installera [!DNL Insight] och konfigurera en anslutning till överordnad [!DNL Insight Server] enligt beskrivningen i *[!DNL Insight]Användarhandbok*.
