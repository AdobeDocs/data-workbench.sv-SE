---
description: Insight Servers klienter (Report and Insight) använder vanliga namn för att hänvisa till Insight Servers.
title: Definiera serverns nätverksplats
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Definiera serverns nätverksplats{#defining-the-server-s-network-location}

Insight Servers klienter (Report and Insight) använder vanliga namn för att hänvisa till Insight Servers.

När du till exempel ansluter [!DNL Insight] eller [!DNL Report] till en [!DNL Insight Server] identifierar du servern med dess vanliga namn (till exempel [!DNL Server.MyCompany.com]). Internt tolkar klienten det vanliga namnet till en numerisk IP-adress innan den skickar en begäran till servern.

För att matcha vanliga namn till IP-adresser använder [!DNL Insight Server’s]-klienter en lokal sökfil som kallas adressfilen. Adressfilen innehåller de vanliga namnen för [!DNL Insight Servers] som är installerade på din organisation och identifierar deras numeriska IP-adresser. En klient får automatiskt en kopia av adressfilen när den öppnar en profil på [!DNL Insight Server].

När en klient skickar en begäran till en [!DNL Insight Server] försöker klienten att matcha serverns vanliga namn med adressfilen. Om adressfilen identifierar en IP-adress för den begärda servern skickar klienten begäran till den angivna adressen. Om adressen inte är definierad (adressfilen definierar t.ex. inte serverns namn) misslyckas begäran. Du kan även konfigurera klienter så att adresserna löses via operativsystemets DNS-mekanism (Domain Naming Service) om inget namn definieras i klientens adressfil. Instruktioner finns i parametern Parent i tabellen [NetworkLocation Parameters](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) i följande avsnitt.
