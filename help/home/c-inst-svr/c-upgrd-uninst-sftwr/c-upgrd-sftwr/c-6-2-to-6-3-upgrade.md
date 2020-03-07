---
description: Uppgraderar serverkomponenter för Data Workbench 6.3.
title: DWB Server upgrade 6.2 to 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# DWB Server-uppgradering: 6.2 till 6.3{#dwb-server-upgrade-to}

Uppgraderar serverkomponenter för Data Workbench 6.3.

**Uppgraderingsserver**

Om du har anpassade profiler som har företräde framför standardfilerna i [!DNL Base] paketet måste du uppdatera dessa anpassade filer:

* **Uppdatera Meta.cfg-filen** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]för att ange uppdaterad lösenordskryptering för FSU-servern) och för att lägga till poster för Namnvärdespar för att dra nytta av [frågesträngsgrupperingar](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. Öppna [!DNL meta.cfg] filen på FSU:n.
   1. Ändra datatypen för **[!UICONTROL Proxy Password]** från [!DNL string"] till [!DNL EncryptedString]i avsnittet *Arbetsstationskonfiguration* .

      ```
      Proxy User Name = string: 
      Proxy Password = EncryptedString:   ( 
      
<i>from Proxy Password = String</i>)Use Address File = bool: true&quot;

    1. Lägg till nya poster för att aktivera de nya Namnvärdespar-omformningarna: *BuildNameValuePair* och *ExtractNameValuePairs*.
    
    Öppna en arbetsyta och högerklicka på **Admin** > **Profile Manager**.
    
    Under **Context** klickar du på filen **meta.cfg** i kolumnen **Base** och sedan på **Make Local**. I kolumnen med användartabellen högerklickar du och väljer **Open** > **in Workstation**.
    
    ![](assets/meta_cfg.png)
    
    * I det nya fönstret klickar du på **metadata** och lägger till godkända underordnade mallar.
    
    ![](assets/meta_cfg_child.png)
    
    * Öppna **transformation** och lägg till nya mallar.
    
    ![](assets/meta_cfg_template.png)

* **Uppdatering för snabbsammanslagningsförbättringar**. Lägg till parametrar eller ändra värden i följande konfigurationsfiler för att utnyttja hastighetsförbättringarna i Data Workbench under en omformning.

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:  
          URI = string: /SourceListServer/ 
          Listing Interval = int: 10 ( 
      <new>)
      ```

   * **Disk Files.cfg** (at [!DNL E:\Server\Components] och [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024  
      <(from double: 256)> 
      Disk Cache Read Limit (MB) = double: 768  
      <(new)>
      ```

   * **Loggbehandlingsläge.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed) 
      Batch Bytes = int: 268435456 
      Cloud Bytes = int: 268435456 
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      ( 
      <new>) 
      Cache Bytes = int: 32000000 
      Fast Input Decision Ratio = double: 200 
      Fast Input FIFO Bytes = int: 268435456 
      FIFO Hash Mask = int: 16383 
      Fast Merge Buffer Bytes = int: 536870912 
      Slow Merge Buffer Bytes = int: 268435456 
      Fast Merge Fan In = int: 64 
      Key Cache Size Logarithm = int: 21 
      Max Seeks = int: 512 
      Output Old Buffer Bytes = int: 536870912 
      Overflow FIFO Bytes = int: 67108864 
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >Om du vill dra nytta av förbättringarna av Snabbsammanslagning måste du ha minst 8 GB RAM per DPU.

* **Adobe Target med DWB-integreringsuppdatering**. En ny exportfil, [!DNL ExportIntegration.exe], ersätter den befintliga [!DNL TnTSend.exe] filen på Insight Server (`E:\Server\Scripts\TnTSend.exe`). Den nya exportfilen har stöd för både [Adobe Target](https://www.adobe.com/marketing/target.html) -integrering och samordning med den nya Master Marketing Profile (MMP) och [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   Du måste uppdatera följande kommandon för export till Adobe Target.

   `Command = string: TnTSend.exe`

   till

   ```
   <filepath>
   Command = string: ExportIntegration.exe 
   </filepath>
   ```

   >[!NOTE]
   >
   >Detta påverkar endast exporter som skapats före version 6.3.

   Du kan också prova följande för att använda den gamla exportprocessen:

   * Skapa en ny test- och målexport på arbetsstationen.
   * Ändra den gamla Test- och Target-exporten i [!DNL Server/Profiles/`<your profile>`/Export.]

* **Uppdatera Adobe SC-profilen.** Ändringar i [!DNL Exclude Hit.cfg] filen kräver att ett fält deklareras i den associerade [!DNL Decoding Instructions.cfg] filen.

   >[!NOTE]
   >
   >Om din Adobe SC-profil innehåller en anpassad [!DNL Decoding Instructions.cfg] fil måste du inkludera en [!DNL DelimitedDecoder] parameter i den anpassade filen.

   ```
   0 = DelimitedDecoder: 
      Delimiter = string: \t 
      Fields = vector: x items 
      …  
         5 = string: 
   Changed to: 
   
   5 = string: x-hit_source
   ```

   Genom att lägga till [!DNL DelimitedDecoder] fältet kan du dra nytta av funktionsuppdateringar och undvika eventuella loggbearbetningsproblem som uppstår till följd av dessa uppdateringar.
