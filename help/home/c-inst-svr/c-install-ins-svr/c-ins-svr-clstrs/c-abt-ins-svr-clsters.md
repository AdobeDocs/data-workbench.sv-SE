---
description: Ett Insight Server-kluster krävs när den mängd data som du vill bearbeta och göra tillgänglig för dina användare av Insight och Report överskrider kapaciteten för en enskild Insight-server.
title: Om Insight Server Clusters
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# Om Insight Server Clusters{#about-insight-server-clusters}

{{eol}}

Ett Insight Server-kluster krävs när den mängd data som du vill bearbeta och göra tillgänglig för dina användare av Insight och Report överskrider kapaciteten för en enskild Insight-server.

Genom att ställa in en [!DNL Insight Server] kan du distribuera en enda analysdatauppsättning till flera datorer i ett kluster för att utnyttja processorkraften hos flera [!DNL Insight Servers].

Det första steget i genomförandet av en [!DNL Insight Server] klustret ska allokera [!DNL Insight Server] datorer i klustret. Den första [!DNL Insight Server] datorn som du konfigurerar är din överordnad [!DNL Insight Server] (kallas ibland din primära [!DNL Insight Server]).

>[!NOTE]
>
>Om du använder en [!DNL Insight Server] Filserverenhet (FSU), Adobe rekommenderar att du konfigurerar FSU som din överordnad [!DNL Insight Server]. Mer information om hur du konfigurerar en FSU finns i *Konfigurationshandbok för datauppsättning*.

Överordnad [!DNL Insight Server] hanterar kommunikationen mellan de andra [!DNL Insight Servers] i klustret (kallas bearbetningsservrar eller ibland frågeservrar) och instanser av [!DNL Insight] och [!DNL Report]. För en given datauppsättning utförs bearbetning av loggfiler på (en eller flera) angivna [!DNL Insight Servers] (överordnad eller bearbetning) enligt specifikationen i [!DNL Insight Server] konfigurationsfiler. När du arbetar i en klustermiljö [!DNL Insight] installationerna är konfigurerade för att komma åt överordnad [!DNL Insight Server], men frågor kan hanteras av någon av [!DNL Insight Servers] i klustret.

>[!NOTE]
>
>The **PAServer.cfg** -fil. Om du vill skicka Predictive Analytics-klusterjobb till Insight-servrar måste du konfigurera [!DNL PAServer.cfg] -fil för hantering av klusteröverföringar på serversidan. Den anpassade profilen ska ärva [!DNL PAServer.cfg] från Predictive Analytics-profilen ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Ange en *Överordnad server* i den här filen och spara [!DNL PAServer.cfg] till implementeringsplatsen.
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
>Instruktionerna i det här kapitlet gäller inte när en [!DNL Insight Server] kluster bestående av mer än fem (5) [!DNL Insight Servers]. Kontakta Adobe för att få systemkrav och rekommendationer för profilkonfiguration för kluster som är större än fem [!DNL Insight Servers].
