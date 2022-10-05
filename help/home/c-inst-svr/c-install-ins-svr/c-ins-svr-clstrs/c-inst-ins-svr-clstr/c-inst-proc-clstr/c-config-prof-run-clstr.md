---
description: När du konfigurerar en datauppsättningsprofil att köras på ett Insight Server-kluster delar alla datorer i klustret alla datauppsättningskonfigurationsfiler för den profilen.
title: Konfigurera en profil som ska köras i ett kluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Konfigurera en profil som ska köras i ett kluster{#configuring-a-profile-to-run-on-a-cluster}

{{eol}}

När du konfigurerar en datauppsättningsprofil att köras på ett Insight Server-kluster delar alla datorer i klustret alla datauppsättningskonfigurationsfiler för den profilen.

Posterna för parametrarna i dessa filer måste därför gälla för alla [!DNL Insight Servers] i klustret. Till exempel platsen för de loggfiler som ska läsas, de sökfiler som ska användas av [!DNL Insight Server]och platsen för utdata från [!DNL Insight Server] måste vara samma på alla datorer i klustret.

Du utför alla konfigurationsåtgärder på klustrets överordnad [!DNL Insight Server], vilket är [!DNL Insight Server] använder du för att redigera konfigurationsfilerna. Alla ändringar av den sparade konfigurationsfilen som gjorts på överordnad [!DNL Insight Server] synkroniseras automatiskt med filerna som bearbetas [!DNL Insight Servers] i klustret.

Så här kör du en datauppsättningsprofil på en [!DNL Insight Server] måste du utföra följande processer i den ordning som anges:

1. [Avgöra vilka INSIE-servrar som hanterar händelsedata](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Ange bearbetningsservrar i Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Vid behov) [Ändra konfigurationsfilerna för datauppsättningen för profilen](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Avgöra vilka INSIE-servrar som hanterar händelsedata {#section-59b8e3f2b34f49739d544c8740a62fba}

Det är inte nödvändigt att alla [!DNL Insight Servers] i klusterprocesshändelsedata. Du kan välja en [!DNL Insight Server] i klustret som en filserverenhet som lagrar källfilerna (VSL- och loggfiler) och skickar filerna till alla databehandlingsenheter (bearbetningsservrar) i klustret. Den här installationen ger fördelen med ett enda händelsedatalager och drar nytta av bearbetningskraften hos alla bearbetningsservrar i klustret. Bearbetningsservrarna delar datafilerna mellan sig och ser till att samma fil inte bearbetas mer än en gång.

Mer information om hur du anger en [!DNL Insight Server] för att köras som en filserverenhet, se kapitlet Loggbearbetningskonfigurationsfil i *Konfigurationshandbok för datauppsättning*.

Om du bestämmer dig för att lagra källdatafiler på var och en av bearbetningsservrarna i stället för på en enda filserverenhet, måste du dela upp filerna jämnt mellan bearbetningsservrarna. Lagra inte alla datauppsättningens källfiler på var och en av bearbetningsservrarna. Om flera kopior av samma fil är tillgängliga för flera bearbetningsservrar, läses data flera gånger (en gång per dator) och dina data skevas.

För att avgöra vem [!DNL Insight Servers] om du vill bearbeta loggfiler, kontakta Adobe Consulting.

## Ange bearbetningsservrar i Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

I [!DNL profile.cfg] anger du de bearbetningsservrar som bearbetar data för profilen.

**Så här öppnar du filen profile.cfg**

Du kommer åt profilkonfigurationsfilen med [!DNL Profile Manager] in [!DNL Insight].

1. Öppna dialogrutan [!DNL Profile Manager] genom att högerklicka på en arbetsyta och klicka **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** eller genom att öppna arbetsytan Profilhantering på [!DNL Admin] -fliken.

1. I [!DNL Profile Manager], högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.

1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret för profilkonfiguration visas.

**Lägga till bearbetningsservrar**

1. I [!DNL profile.cfg] fil, klicka **[!UICONTROL Profile]** och sedan klicka **[!UICONTROL Processing Servers]** för att visa innehållet.

1. Högerklicka **[!UICONTROL Processing Servers]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. I parametern Gemensamt namn skriver du det vanliga namnet för den första bearbetningsservern i klustret. Exempel: [!DNL server1.mycompany.com]
1. Upprepa steg 2 och 3 tills du har lagt till de gemensamma namnen för alla bearbetningsservrar i klustret.

   >[!NOTE]
   >
   >Om överordnad [!DNL Insight Server] bearbetar data, du måste också lägga till dem.

1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

1. Högerklicka på bockmarkeringen i dialogrutan [!DNL User] kolumn intill [!DNL profile.cfg]. Klicka på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Ändra konfigurationsfilerna för datauppsättningen för profilen {#section-99bf9248e4e5483cb518f453b0a2f278}

**Så här ändrar du datauppsättningens konfigurationsfiler**

Om du behöver göra ändringar i datauppsättningens konfigurationsfiler ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], datauppsättningen innehåller filer, [!DNL Log Processing Mode.cfg]och så vidare), gör du det bara på överordnad [!DNL Insight Server].

1. Öppna de filer du vill ändra:

   Instruktioner om hur du kommer åt filerna finns i *Konfigurationshandbok för datauppsättning*.
1. Gör ändringarna. Se *Konfigurationshandbok för datauppsättning* om du vill ha information om parametrarna i konfigurationsfilerna.
1. Spara filen.

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. Högerklicka på bockmarkeringen i dialogrutan [!DNL User] -kolumnen bredvid filnamnet.
   1. Klicka **[!UICONTROL Save to]** och välj önskad profil.

>[!NOTE]
>
>[!DNL Insight] användare som har åtkomst till en datauppsättningsprofil som körs i ett kluster identifierar endast de överordnad [!DNL Insight Server] i [!DNL Insight] konfigurationsfil ( [!DNL insight.cfg]). Med tanke på [!DNL Insight] användare, kan profilen bara nås av en [!DNL Insight Server] (överordnad [!DNL Insight Server]). kan dock förfrågningar från analytiker dirigeras till någon av [!DNL Insight Servers] i klustret.

An [!DNL Insight Server] kluster möjliggör centraliserad lagring av [!DNL .vsl] loggfiler (från [!DNL Sensor]) på en [!DNL Insight Server] datorn anropade en filserverenhet (FSU). Mer information om hur du installerar en FSU finns i [Installationsprocedurer för en Insight Server FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Mer information om hur du konfigurerar en FSU finns i *Konfigurationshandbok för datauppsättning*.
