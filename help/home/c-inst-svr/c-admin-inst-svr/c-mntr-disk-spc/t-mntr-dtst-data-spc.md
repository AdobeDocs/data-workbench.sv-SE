---
description: Information om övervakning av datauppsättningar och tillägg av nya platser för datalagring av datauppsättningar.
title: Övervaka datauppsättningsdataområde
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 0%

---

# Övervaka datauppsättningsdatautrymme{#monitoring-dataset-data-space}

Information om övervakning av datauppsättningar och tillägg av nya platser för datalagring av datauppsättningar.

**Rekommenderad frekvens:** var 5-10:e minut

Som standard skriver [!DNL Insight Server] sin datauppsättning till [!DNL temp.db]-filen på samma enhet som [!DNL Insight Server]-programfilerna på databehandlingsenheten. Mängden datauppsättningsdata per [!DNL Insight Server]-dator är begränsad till följande, beroende på vilket som inträffar först:

* Fem hundra (500) miljoner poster med data som matats in i den datauppsättningen
* 500 GB lagrade data
* En (1) MB datauppsättningsdata lagras per en dimension på rotnivå (till exempel 5 000 poster per besökare i genomsnitt 200 byte per post)

Om du vill att [!DNL Insight Server] ska underhålla datauppsättningen på en annan enhet, eller om den datamängd du förväntar dig ska samla in kräver att flera enheter används, måste du uppdatera konfigurationsfilen för diskfiler ( [!DNL Disk Files.cfg]) för att ange var du vill att [!DNL Insight Server] ska skriva [!DNL temp.db]-filerna. Filen [!DNL Disk Files.cfg] visar diskfilerna (en vektor med strängar) och anger platsen för datauppsättningsdata som används av [!DNL Insight Server] under ombearbetningen och åtgärden. Det finns vanligtvis en fil per fysisk enhet.

>[!NOTE]
>
>Innehållet i [!DNL Disk Files.cfg]-filen kan ha ändrats under installationen av [!DNL Insight Server]. Mer information finns i [Konfigurera platsen för datauppsättningen (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Lägga till nya platser för datalagring för datauppsättning**

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Insight Server] som du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. Klicka på **[!UICONTROL Components]** i [!DNL Server Files Manager] för att visa innehållet. Filen [!DNL Disk Files.cfg] finns i den här katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *servernamn* för [!DNL Disk Files.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i kolumnen [!DNL Temp] för [!DNL Disk Files.cfg].
1. Högerklicka på den nya bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. I fönstret [!DNL Disk Files.cfg] klickar du på **[!UICONTROL component]** för att visa innehållet.

   ![Steginformation](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Parametern Identifiera diskfel är som standard inställd på true. Parametern Skivcachestorlek (MB) styr mängden minne som används av [!DNL Insight Server] för att öka diskåtkomsthastigheten och är som standard inställd på 128. Kontakta Adobe innan du ändrar någon av dessa parametrar.

1. Om du vill ändra diskfilerna på [!DNL Insight Server]-datorn högerklickar du på **[!UICONTROL Disk Files]** och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Om du vill ta bort en diskfil högerklickar du på diskfilsnumret och klickar på **[!UICONTROL Remove]**.

1. För den nya diskfilen anger du katalogen och namnet på filen som ska användas av [!DNL Insight Server] under ombearbetningen och åtgärden.

   ![Steginformation](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Parametern Identifiera diskfel är som standard inställd på true. Parametern Skivcachestorlek (MB) styr mängden minne som används av [!DNL Insight Server] för att öka diskåtkomsthastigheten och är som standard inställd på 128. Kontakta Adobe innan du ändrar någon av dessa parametrar.

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
