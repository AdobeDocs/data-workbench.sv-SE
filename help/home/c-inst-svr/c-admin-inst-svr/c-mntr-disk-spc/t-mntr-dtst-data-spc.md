---
description: Information om övervakning av datauppsättningar och tillägg av nya platser för datalagring av datauppsättningar.
title: Övervaka datauppsättningsdataområde
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 0%

---

# Övervaka datauppsättningsdataområde{#monitoring-dataset-data-space}

{{eol}}

Information om övervakning av datauppsättningar och tillägg av nya platser för datalagring av datauppsättningar.

**Rekommenderad frekvens:** Var 5-10:e minut

Som standard [!DNL Insight Server] skriver sin datauppsättning till [!DNL temp.db] på samma enhet som [!DNL Insight Server] programfiler på databehandlingsenheten. Mängden datauppsättningsdata per [!DNL Insight Server] maskinen är begränsad till följande, beroende på vilket som inträffar först:

* Fem hundra (500) miljoner poster med data som matats in i den datauppsättningen
* 500 GB lagrade data
* En (1) MB datauppsättningsdata lagras per en dimension på rotnivå (till exempel 5 000 poster per besökare i genomsnitt 200 byte per post)

Om du vill [!DNL Insight Server] om du vill underhålla datauppsättningen på en annan enhet, eller om den datamängd du förväntar dig ska samla in kräver att flera enheter används, måste du uppdatera konfigurationsfilen för diskfiler ( [!DNL Disk Files.cfg]) för att ange var du vill [!DNL Insight Server] för att skriva [!DNL temp.db] fil(er). The [!DNL Disk Files.cfg] -filen visar diskfilerna (en vektor med strängar) och anger platsen för datauppsättningsdata som används av [!DNL Insight Server] under upparbetning och drift. Det finns vanligtvis en fil per fysisk enhet.

>[!NOTE]
>
>Innehållet i [!DNL Disk Files.cfg] filen kan ha ändrats under installationen [!DNL Insight Server]. Mer information finns i [Konfigurera platsen för datauppsättningen (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Lägga till nya platser för datalagring för datauppsättning**

1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Insight Server] du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL Disk Files.cfg] filen finns i den här katalogen.
1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn för [!DNL Disk Files.cfg] och klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Disk Files.cfg].
1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. I [!DNL Disk Files.cfg] fönster, klicka **[!UICONTROL component]** för att visa innehållet.

   ![Steginformation](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Parametern Identifiera diskfel är som standard inställd på true. Parametern Diskcachestorlek (MB) styr mängden minne som [!DNL Insight Server] använder för att öka diskens åtkomsthastighet och är som standard inställd på 128. Kontakta Adobe innan du ändrar någon av dessa parametrar.

1. Så här ändrar du skivfilerna på [!DNL Insight Server] dator, högerklicka **[!UICONTROL Disk Files]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Om du vill ta bort en diskfil högerklickar du på filnumret och klickar på **[!UICONTROL Remove]**.

1. För den nya diskfilen anger du katalogen och namnet på filen som ska användas av [!DNL Insight Server] under upparbetning och drift.

   ![Steginformation](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Parametern Identifiera diskfel är som standard inställd på true. Parametern Diskcachestorlek (MB) styr mängden minne som [!DNL Insight Server] använder för att öka diskens åtkomsthastighet och är som standard inställd på 128. Kontakta Adobe innan du ändrar någon av dessa parametrar.

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL Temp] kolumn och markera **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
