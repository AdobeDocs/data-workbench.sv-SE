---
description: Datamängdskatalogen innehåller ytterligare filer som antingen krävs för att programvaran ska fungera eller som tillhandahåller ytterligare funktioner för implementeringen av Adobe.
title: Andra filer
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Andra filer{#other-files}

{{eol}}

Datamängdskatalogen innehåller ytterligare filer som antingen krävs för att programvaran ska fungera eller som tillhandahåller ytterligare funktioner för implementeringen av Adobe.

* **[!DNL Client.cfg:]** The [!DNL Client.cfg] i datauppsättningskatalogen för [!DNL Base] profil krävs för att programvaran ska fungera. Ta inte bort eller ändra någon av parametrarna i dialogrutan [!DNL Client.cfg] -fil.

* **[!DNL Cluster.cfg:]** The [!DNL Cluster.cfg] i datauppsättningskatalogen för [!DNL Base] profil krävs för att programvaran ska fungera. I [!DNL Cluster.cfg] bör du bara ändra parametern Normalize Server om du konfigurerar en datauppsättning som ska bearbetas i ett data workbench-serverkluster. Instruktioner om hur du ändrar parametern Normalisera server finns i [Skapa en central normaliseringsserver för ett kluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]och [!DNL Insight Transform Mode.cfg]:** Om du använder omvandlingsfunktioner har du ytterligare två konfigurationsfiler, data workbench [!DNL Transform.cfg] och data workbench [!DNL TransformMode.cfg], i datauppsättningskatalogen för [!DNL Transform] profil. Mer information om de här filerna och deras parametrar finns i [Omformningsfunktioner](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* The **PAServer.cfg** -fil. Om du vill skicka Predictive Analytics-klusterjobb till Insight-servrar måste du konfigurera [!DNL PAServer.cfg] -fil för hantering av klusteröverföringar på serversidan.
Den anpassade profilen ska ärva [!DNL PAServer.cfg] från Predictive Analytics-profilen ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Ange en *Överordnad server* i den här filen och spara [!DNL PAServer.cfg] till implementeringsplatsen.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
