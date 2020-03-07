---
description: Information om övervakning av datauppsättningar och tillägg av nya platser för datalagring av datauppsättningar.
solution: Insight
title: Övervaka datauppsättningsdataområde
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Övervaka datauppsättningsdataområde{#monitoring-dataset-data-space}

Information om övervakning av datauppsättningar och tillägg av nya platser för datalagring av datauppsättningar.

**Rekommenderad frekvens:** Var 5-10:e minut

Som standard skriver [!DNL Insight Server] sin datauppsättning till [!DNL temp.db] filen på samma enhet som [!DNL Insight Server] programfilerna på databehandlingsenheten. Mängden datauppsättningsdata per [!DNL Insight Server] dator är begränsad till följande, beroende på vilket som inträffar först:

* Fem hundra (500) miljoner poster med data som matats in i den datauppsättningen
* 500 GB lagrade data
* En (1) MB datauppsättningsdata lagras per en dimension på rotnivå (till exempel 5 000 poster per besökare i genomsnitt 200 byte per post)

Om du vill [!DNL Insight Server] underhålla datauppsättningen på en annan enhet, eller om mängden data som ska samlas in kräver användning av flera enheter, måste du uppdatera konfigurationsfilen för diskfiler ( [!DNL Disk Files.cfg]) för att ange var du vill [!DNL Insight Server] skriva [!DNL temp.db] filerna. I [!DNL Disk Files.cfg] filen visas diskfilerna (en vektor med strängar) och platsen för datauppsättningsdata som används av [!DNL Insight Server] under ombearbetningen och åtgärden anges. Det finns vanligtvis en fil per fysisk enhet.

>[!NOTE]
>
>Innehållet i [!DNL Disk Files.cfg] filen kan ha ändrats under installationen [!DNL Insight Server]. Mer information finns i [Konfigurera platsen för datauppsättningen (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Lägga till nya platser för datalagring för datauppsättning**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för det [!DNL Insight Server] du vill konfigurera och klicka sedan på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL Disk Files.cfg] katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* för [!DNL Disk Files.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Disk Files.cfg].
1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Klicka i [!DNL Disk Files.cfg] fönstret **[!UICONTROL component]** för att visa innehållet.

   ![Steginformation](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Parametern Identifiera diskfel är som standard inställd på true. Parametern Skivcachestorlek (MB) styr mängden minne som [!DNL Insight Server] används för att öka diskens åtkomsthastighet och är som standard inställd på 128. Kontakta Adobe innan du ändrar någon av dessa parametrar.

1. Om du vill ändra diskfilerna på [!DNL Insight Server] datorn högerklickar du **[!UICONTROL Disk Files]** och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Om du vill ta bort en diskfil högerklickar du på diskfilsnumret och klickar på **[!UICONTROL Remove]**.

1. För den nya diskfilen anger du katalogen och namnet på den fil som ska användas [!DNL Insight Server] under ombearbetningen och åtgärden.

   ![Steginformation](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Parametern Identifiera diskfel är som standard inställd på true. Parametern Skivcachestorlek (MB) styr mängden minne som [!DNL Insight Server] används för att öka diskens åtkomsthastighet och är som standard inställd på 128. Kontakta Adobe innan du ändrar någon av dessa parametrar.

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

