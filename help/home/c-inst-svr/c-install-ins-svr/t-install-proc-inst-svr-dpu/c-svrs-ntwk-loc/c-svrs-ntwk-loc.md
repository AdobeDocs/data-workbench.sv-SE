---
description: Insight Servers klienter (Report and Insight) använder vanliga namn för att hänvisa till Insight Servers.
title: Definiera serverns nätverksplats
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Definiera serverns nätverksplats{#defining-the-server-s-network-location}

{{eol}}

Insight Servers klienter (Report and Insight) använder vanliga namn för att hänvisa till Insight Servers.

Exempel: När du ansluter [!DNL Insight] eller [!DNL Report] till [!DNL Insight Server]identifierar du servern med dess vanliga namn (till exempel [!DNL Server.MyCompany.com]). Internt tolkar klienten det vanliga namnet till en numerisk IP-adress innan den skickar en begäran till servern.

Så här löser du vanliga namn till IP-adresser: [!DNL Insight Server’s] klienterna använder en lokal uppslagsfil som kallas adressfilen. Adressfilen innehåller vanliga namn för [!DNL Insight Servers] installerade på din organisation och identifierar deras numeriska IP-adresser. En klient får automatiskt en kopia av adressfilen när den öppnar en profil på [!DNL Insight Server].

När en klient skickar en begäran till en [!DNL Insight Server]försöker den att lösa serverns namn genom adressfilen. Om adressfilen identifierar en IP-adress för den begärda servern skickar klienten begäran till den angivna adressen. Om adressen inte är definierad (adressfilen definierar t.ex. inte serverns namn) misslyckas begäran. Du kan även konfigurera klienter så att adresserna löses via operativsystemets DNS-mekanism (Domain Naming Service) om inget namn definieras i klientens adressfil. Instruktioner finns i parametern Överordnad i [Parameterregister för NetworkLocation](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) i följande avsnitt.
