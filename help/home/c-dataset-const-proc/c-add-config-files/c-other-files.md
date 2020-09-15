---
description: Datamängdskatalogen innehåller ytterligare filer som antingen krävs för att programvaran ska fungera eller som tillhandahåller ytterligare funktioner för implementeringen av Adobe.
solution: Analytics
title: Andra filer
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---


# Andra filer{#other-files}

Datamängdskatalogen innehåller ytterligare filer som antingen krävs för att programvaran ska fungera eller som tillhandahåller ytterligare funktioner för implementeringen av Adobe.

* **[!DNL Client.cfg:]** Filen i [!DNL Client.cfg] datauppsättningskatalogen för [!DNL Base] profilen krävs för att programvaran ska fungera. Ta inte bort eller ändra någon av parametrarna i [!DNL Client.cfg] filen.

* **[!DNL Cluster.cfg:]** Filen i [!DNL Cluster.cfg] datauppsättningskatalogen för [!DNL Base] profilen krävs för att programvaran ska fungera. I [!DNL Cluster.cfg] filen bör du bara ändra parametern Normalisera server om du konfigurerar en datauppsättning som ska bearbetas i ett datalägesserverkluster. Instruktioner om hur du ändrar parametern Normalisera server finns i [Skapa en central normaliseringsserver för ett kluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]och[!DNL Insight Transform Mode.cfg]:** Om du använder omformningsfunktioner har du ytterligare två konfigurationsfiler, data workbench [!DNL Transform.cfg] och data workbench, [!DNL TransformMode.cfg]i DataSet-katalogen för [!DNL Transform] profilen. Mer information om de här filerna och deras parametrar finns i [Omforma funktioner](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Filen **PAServer.cfg** . Om du vill skicka Predictive Analytics-klusterjobb till Insight-servrar måste du konfigurera [!DNL PAServer.cfg] filen för hantering av klusteröverföringar på serversidan.
Den anpassade profilen ska ärva profilen [!DNL PAServer.cfg] från Predictive Analytics-profilen ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Ange en *Överordnad server* i den här filen och spara [!DNL PAServer.cfg] den på implementeringsplatsen.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```

