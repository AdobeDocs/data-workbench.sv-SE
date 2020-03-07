---
description: Ett Insight Server-kluster krävs när den mängd data som du vill bearbeta och göra tillgänglig för dina användare av Insight och Report överskrider kapaciteten för en enskild Insight-server.
solution: Insight
title: Om Insight Server Clusters
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Om Insight Server Clusters{#about-insight-server-clusters}

Ett Insight Server-kluster krävs när den mängd data som du vill bearbeta och göra tillgänglig för dina användare av Insight och Report överskrider kapaciteten för en enskild Insight-server.

Genom att konfigurera ett [!DNL Insight Server] kluster kan du distribuera en enda analysdatauppsättning till flera datorer i ett kluster för att utnyttja processorkraften hos flera olika [!DNL Insight Servers].

Det första steget i implementeringen av ett [!DNL Insight Server] kluster är att allokera datorerna [!DNL Insight Server] i klustret. Den första [!DNL Insight Server] datorn som du konfigurerar är din huvuddator [!DNL Insight Server] (kallas ibland din primära [!DNL Insight Server]).

>[!NOTE]
>
>Om du använder en [!DNL Insight Server] filserverenhet (FSU) bör du konfigurera FSU:n som huvudserver [!DNL Insight Server]. Mer information om hur du konfigurerar en FSU finns i *konfigurationsguiden* för datauppsättningar.

Huvudservern [!DNL Insight Server] hanterar kommunikationen mellan de andra [!DNL Insight Servers] i klustret (kallas för bearbetningsservrar eller ibland frågeservrar) och instanser av [!DNL Insight] och [!DNL Report]. För en given datauppsättning utförs bearbetning av loggfiler på (en eller flera) angiven [!DNL Insight Servers] (master eller processing) enligt [!DNL Insight Server] konfigurationsfilerna. När du arbetar i en klustrad miljö är installationerna konfigurerade för att komma åt huvudservern [!DNL Insight] men frågor kan hanteras av alla [!DNL Insight Server][!DNL Insight Servers] i klustret.

>[!NOTE]
>
>Filen **PAServer.cfg** . Om du vill skicka Predictive Analytics-klusterjobb till Insight-servrar måste du konfigurera [!DNL PAServer.cfg] filen för hantering av klusteröverföringar på serversidan. Den anpassade profilen ska ärva profilen [!DNL PAServer.cfg] från Predictive Analytics-profilen ( [!DNL Server\Profiles\Predictive Analytics\Dataset]). Ange en *huvudserver* i den här filen och spara [!DNL PAServer.cfg] den på implementeringsplatsen. >
>
```>
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```>



>[!IMPORTANT]
>
>Instruktionerna i detta kapitel gäller inte skapande av ett [!DNL Insight Server] kluster som består av mer än fem (5) [!DNL Insight Servers]. Kontakta Adobe för att få systemkrav och rekommendationer för profilinställningar för kluster som är större än fem [!DNL Insight Servers].

