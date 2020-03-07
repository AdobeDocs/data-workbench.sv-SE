---
description: Om du vill använda ett kluster måste du utse en Insight-server i klustret till master Insight Server.
solution: Insight
title: Installera Master Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installera Master Insight Server{#installing-the-master-insight-server}

Om du vill använda ett kluster måste du utse en Insight-server i klustret till master Insight Server.

En klientkomponent som [!DNL Insight] eller [!DNL Report] ansluter till huvudsidan [!DNL Insight Server] i början av en session. Vid efterföljande punkter under sessionen kan klienten ansluta till andra [!DNL Insight Servers] i klustret för att utföra en fråga. De efterföljande anslutningarna mellan klienten och den andra [!DNL Insight Servers] i klustret förmedlas av huvudservern [!DNL Insight Server] och är genomskinliga för klienten.

Förutom att förmedla anslutningar mellan en klient och andra [!DNL Insight Servers] i klustret fungerar huvudservern [!DNL Insight Server] som central administrativ punkt för hela klustret. När du administrerar ett kluster uppdaterar du huvudklustret [!DNL Insight Server]. De administrativa ändringar som du gör i huvudkatalogen [!DNL Insight Server] hämtas av den andra [!DNL Insight Servers] i klustret.

**Installera mallsidan[!DNL Insight Server]**

1. Bestäm vilken dator som ska fungera som huvuddator [!DNL Insight Server].
1. Installera och konfigurera [!DNL Insight Server] (vanligtvis en [!DNL Insight Server] FSU) på den här datorn enligt beskrivningen i [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. Installera [!DNL Insight] och konfigurera en anslutning till mallsidan [!DNL Insight Server] enligt beskrivningen i *[!DNL Insight]användarhandboken *.
