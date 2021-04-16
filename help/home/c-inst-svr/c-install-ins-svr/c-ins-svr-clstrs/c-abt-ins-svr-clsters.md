---
description: Ett Insight Server-kluster krävs när den mängd data som du vill bearbeta och göra tillgänglig för dina användare av Insight och Report överskrider kapaciteten för en enskild Insight-server.
title: Om Insight Server Clusters
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# Om Insight Server Clusters{#about-insight-server-clusters}

Ett Insight Server-kluster krävs när den mängd data som du vill bearbeta och göra tillgänglig för dina användare av Insight och Report överskrider kapaciteten för en enskild Insight-server.

Genom att konfigurera ett [!DNL Insight Server]-kluster kan du distribuera en enda analysdatauppsättning till flera datorer i ett kluster för att utnyttja processorkraften hos flera [!DNL Insight Servers].

Det första steget i implementeringen av ett [!DNL Insight Server]-kluster är att allokera [!DNL Insight Server]-datorerna i klustret. Den första [!DNL Insight Server]-datorn som du konfigurerar är din överordnad [!DNL Insight Server] (kallas ibland för din primära [!DNL Insight Server]).

>[!NOTE]
>
>Om du använder en [!DNL Insight Server]-filserverenhet (FSU) rekommenderar Adobe att du konfigurerar FSU som din överordnad [!DNL Insight Server]. Mer information om hur du konfigurerar en FSU finns i *Konfigurationshandboken för datauppsättningar*.

Överordnad [!DNL Insight Server] hanterar kommunikationen mellan de andra [!DNL Insight Servers] i klustret (kallas bearbetningsservrar eller ibland frågeservrar) och instanser av [!DNL Insight] och [!DNL Report]. För en given datauppsättning utförs loggfilsbearbetning på (en eller flera) angiven [!DNL Insight Servers] (överordnad eller bearbetning) enligt inställningarna i konfigurationsfilerna för [!DNL Insight Server]. När du arbetar i en klustrad miljö är [!DNL Insight]-installationer konfigurerade för åtkomst till överordnad [!DNL Insight Server], men frågor kan hanteras av någon av [!DNL Insight Servers] i klustret.

>[!NOTE]
>
>Filen **PAServer.cfg**. Om du vill skicka Predictive Analytics-klusterjobb till Insight-servrar måste du konfigurera [!DNL PAServer.cfg]-filen för hantering av klusteröverföringar på serversidan. Den anpassade profilen ska ärva [!DNL PAServer.cfg] från Predictive Analytics-profilen ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Ange en *Överordnad server* i den här filen och spara [!DNL PAServer.cfg] på implementeringsplatsen.
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>Instruktionerna i det här kapitlet gäller inte skapande av ett [!DNL Insight Server]-kluster som består av fler än fem (5) [!DNL Insight Servers]. Kontakta Adobe för att få systemkrav och rekommendationer för profilkonfiguration för kluster som är större än fem [!DNL Insight Servers].
