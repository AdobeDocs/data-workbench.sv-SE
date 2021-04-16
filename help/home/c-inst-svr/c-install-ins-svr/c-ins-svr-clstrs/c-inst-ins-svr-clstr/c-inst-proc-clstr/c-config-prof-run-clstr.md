---
description: När du konfigurerar en datauppsättningsprofil att köras på ett Insight Server-kluster delar alla datorer i klustret alla datauppsättningskonfigurationsfiler för den profilen.
title: Konfigurera en profil som ska köras i ett kluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Konfigurera en profil som ska köras på ett kluster{#configuring-a-profile-to-run-on-a-cluster}

När du konfigurerar en datauppsättningsprofil att köras på ett Insight Server-kluster delar alla datorer i klustret alla datauppsättningskonfigurationsfiler för den profilen.

Därför måste posterna för parametrarna i de här filerna gälla för alla [!DNL Insight Servers] i klustret. Platserna för loggfilerna som ska läsas, sökfilerna som ska användas av [!DNL Insight Server] och platsen för utdata från [!DNL Insight Server] måste vara samma på alla datorer i klustret.

Du utför alla konfigurationsåtgärder på klustrets överordnad [!DNL Insight Server], som är den [!DNL Insight Server] som du använder för att redigera konfigurationsfilerna. Alla sparade konfigurationsfilsändringar som görs på överordnad [!DNL Insight Server] synkroniseras automatiskt till filerna på bearbetningen [!DNL Insight Servers] i klustret.

Om du vill köra en datauppsättningsprofil på ett [!DNL Insight Server]-kluster måste du utföra följande processer i den ordning som anges:

1. [Avgöra vilka INSIE-servrar som hanterar händelsedata](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Ange bearbetningsservrar i Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Om det behövs) [Ändra datauppsättningskonfigurationsfilerna för profilen](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Avgöra vilka INSIE-servrar som hanterar händelsedata {#section-59b8e3f2b34f49739d544c8740a62fba}

Alla [!DNL Insight Servers] i klustret måste inte bearbeta händelsedata. Du kan ange en [!DNL Insight Server] i klustret som en filserverenhet som lagrar källfilerna (VSL- och loggfiler) och skickar filerna till alla databehandlingsenheter (bearbetningsservrar) i klustret. Den här installationen ger fördelen med ett enda händelsedatalager och drar nytta av bearbetningskraften hos alla bearbetningsservrar i klustret. Bearbetningsservrarna delar datafilerna mellan sig och ser till att samma fil inte bearbetas mer än en gång.

Mer information om hur du anger att en [!DNL Insight Server] ska köras som en filserverenhet finns i kapitlet Loggbearbetningskonfigurationsfil i *Konfigurationshandboken för datauppsättningar*.

Om du bestämmer dig för att lagra källdatafiler på var och en av bearbetningsservrarna i stället för på en enda filserverenhet, måste du dela upp filerna jämnt mellan bearbetningsservrarna. Lagra inte alla datauppsättningens källfiler på var och en av bearbetningsservrarna. Om flera kopior av samma fil är tillgängliga för flera bearbetningsservrar, läses data flera gånger (en gång per dator) och dina data skevas.

Kontakta Adobe Consulting för att få hjälp med att avgöra vilken [!DNL Insight Servers] som ska behandla loggfiler.

## Ange bearbetningsservrar i Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

I filen [!DNL profile.cfg] anger du de bearbetningsservrar som bearbetar data för profilen.

**Så här öppnar du filen profile.cfg**

Du kommer åt profilkonfigurationsfilen med [!DNL Profile Manager] i [!DNL Insight].

1. När du arbetar i datauppsättningsprofilen öppnar du [!DNL Profile Manager] genom att högerklicka i en arbetsyta och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** eller genom att öppna arbetsytan Profilhantering på fliken [!DNL Admin].

1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] i [!DNL Profile Manager] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].

1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret för profilkonfiguration visas.

**Lägga till bearbetningsservrar**

1. Klicka på **[!UICONTROL Profile]** i [!DNL profile.cfg]-filen och klicka sedan på **[!UICONTROL Processing Servers]** för att visa innehållet.

1. Högerklicka på **[!UICONTROL Processing Servers]** och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. I parametern Gemensamt namn skriver du det vanliga namnet för den första bearbetningsservern i klustret. Exempel: [!DNL server1.mycompany.com]
1. Upprepa steg 2 och 3 tills du har lagt till de gemensamma namnen för alla bearbetningsservrar i klustret.

   >[!NOTE]
   >
   >Om överordnad [!DNL Insight Server] bearbetar data måste du även lägga till dem.

1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

1. Högerklicka på bockmarkeringen i kolumnen [!DNL User] bredvid [!DNL profile.cfg]. Klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Ändra datauppsättningens konfigurationsfiler för profilen {#section-99bf9248e4e5483cb518f453b0a2f278}

**Så här ändrar du datauppsättningens konfigurationsfiler**

Om du behöver göra ändringar i datauppsättningens konfigurationsfiler ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], datauppsättningen innehåller filer, [!DNL Log Processing Mode.cfg] o.s.v.) gör du det bara på överordnad [!DNL Insight Server].

1. Öppna de filer du vill ändra:

   Instruktioner om hur du kommer åt filerna finns i *Konfigurationshandboken för datauppsättningar*.
1. Gör ändringarna. Mer information om parametrarna i konfigurationsfilerna finns i *Konfigurationshandboken för datauppsättningar*.
1. Spara filen.

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. Högerklicka på bockmarkeringen i kolumnen [!DNL User] bredvid filnamnet.
   1. Klicka på **[!UICONTROL Save to]** och välj önskad profil.

>[!NOTE]
>
>[!DNL Insight] Användare som har åtkomst till en datauppsättningsprofil som körs i ett kluster identifierar endast överordnad  [!DNL Insight Server] i  [!DNL Insight] konfigurationsfilen (  [!DNL insight.cfg]). Ur [!DNL Insight]-användarens perspektiv är profilen tillgänglig endast för en [!DNL Insight Server] (överordnad [!DNL Insight Server]); Frågebegäranden från analytiker kan dock dirigeras till någon av [!DNL Insight Servers] i klustret.

Ett [!DNL Insight Server]-kluster tillåter centraliserad lagring av [!DNL .vsl] loggfiler (från [!DNL Sensor]) på en enskild [!DNL Insight Server]-dator som kallas filserverenhet (FSU). Information om hur du installerar en FSU finns i [Installationsprocedurer för en Insight Server FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Mer information om hur du konfigurerar en FSU finns i *Konfigurationshandboken för datauppsättningar*.
