---
description: Datamängdskatalogen innehåller ytterligare filer som antingen krävs för att programvaran ska fungera eller som tillhandahåller ytterligare funktioner för implementeringen av Adobe.
title: Andra filer
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Andra filer{#other-files}

Datamängdskatalogen innehåller ytterligare filer som antingen krävs för att programvaran ska fungera eller som tillhandahåller ytterligare funktioner för implementeringen av Adobe.

* **[!DNL Client.cfg:]** Filen  [!DNL Client.cfg] i datauppsättningskatalogen för  [!DNL Base] profilen krävs för programvaran. Ta inte bort eller ändra någon av parametrarna i [!DNL Client.cfg]-filen.

* **[!DNL Cluster.cfg:]** Filen  [!DNL Cluster.cfg] i datauppsättningskatalogen för  [!DNL Base] profilen krävs för programvaran. I [!DNL Cluster.cfg]-filen bör du endast ändra parametern Normalisera server om du konfigurerar en datauppsättning som ska bearbetas i ett Data Workbench-serverkluster. Instruktioner om hur du ändrar parametern Normalisera server finns i [Skapa en central normaliseringsserver för ett kluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]och  [!DNL Insight Transform Mode.cfg]:** Om du använder omvandlingsfunktioner har du ytterligare två konfigurationsfiler, data workbench  [!DNL Transform.cfg] och data workbench  [!DNL TransformMode.cfg], i  [!DNL Transform] profilens datauppsättningskatalog. Mer information om de här filerna och deras parametrar finns i [Transformeringsfunktioner](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Filen **PAServer.cfg**. Om du vill skicka Predictive Analytics-klusterjobb till Insight-servrar måste du konfigurera [!DNL PAServer.cfg]-filen för hantering av klusteröverföringar på serversidan.
Den anpassade profilen ska ärva [!DNL PAServer.cfg] från Predictive Analytics-profilen ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Ange en *Överordnad server* i den här filen och spara [!DNL PAServer.cfg] på implementeringsplatsen.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
