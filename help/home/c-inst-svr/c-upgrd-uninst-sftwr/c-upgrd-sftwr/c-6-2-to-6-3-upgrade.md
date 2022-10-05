---
description: Uppgraderar serverkomponenter för Data Workbench 6.3.
title: DWB Server upgrade 6.2 to 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---

# DWB Server-uppgradering: 6.2 till 6.3{#dwb-server-upgrade-to}

{{eol}}

Uppgraderar serverkomponenter för Data Workbench 6.3.

**Uppgraderingsserver**

Om du har anpassade profiler som har företräde framför standardfilerna i [!DNL Base] måste du uppdatera dessa anpassade filer:

* **Uppdatera filen Meta.cfg** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]för att ange uppdaterad lösenordskryptering för filsystemenheten (FSU-servern) och för att lägga till poster för namnvärdesparsomformningarna för att dra nytta av [Frågesträngsgrupperingar](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. Öppna [!DNL meta.cfg] på FSU:n.
   1. Ändra datatypen för **[!UICONTROL Proxy Password]** från &quot; [!DNL string"] till &quot; [!DNL EncryptedString]&quot; i *Konfiguration av arbetsstation* -avsnitt.

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. Lägg till nya poster för att aktivera de nya Namnvärdespar-omformningarna: *BuildNameValuePair* och *ExtractNameValuePairs*.

      Öppna en arbetsyta och högerklicka **Administratör** > **Profilhanteraren**.

      Under **Kontext** klickar du på **meta.cfg** i **Bas** kolumn och klicka sedan på **Gör lokal**. Högerklicka och välj i kolumnen i tabellen Användare **Öppna** > **i Workstation**.

      ![](assets/meta_cfg.png)

      * Klicka på **metadata** och lägg till godtagbara underordnade mallar.

         ![](assets/meta_cfg_child.png)

      * Öppna **omformning** och lägg till nya mallar.

         ![](assets/meta_cfg_template.png)

* **Uppdatering för snabbsammanslagningsförbättringar**. Lägg till parametrar eller ändra värden i följande konfigurationsfiler för att utnyttja hastighetsförbättringarna i Datan Workbench under en omformning.

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:
          URI = string: /SourceListServer/
          Listing Interval = int: 10 (
      <new>)
      ```

   * **Disk Files.cfg** (på [!DNL E:\Server\Components] och [!DNL E:\Server\Components for Processing Servers])

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

* **Adobe Target med DWB-integrationsuppdatering**. En ny exportfil, [!DNL ExportIntegration.exe], ersätter befintlig [!DNL TnTSend.exe] på Insight Server (`E:\Server\Scripts\TnTSend.exe`). Den nya exportfilen stöder båda [Adobe Target](https://www.adobe.com/marketing/target.html) integrering och samordning med den nya Överordnad marknadsföringsprofilen (MMP) och [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   Du måste uppdatera följande kommandon för Adobe Target-export.

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
   * Ändra den gamla Test- och Target-exporten som finns i [!DNL Server/Profiles/`<your profile>`/Exportera.]

* **Uppdatera Adobe SC-profilen.** Ändringar i [!DNL Exclude Hit.cfg] filen kräver att ett fält deklareras i den associerade [!DNL Decoding Instructions.cfg] -fil.

   >[!NOTE]
   >
   >Om din Adobe SC-profil innehåller en anpassad [!DNL Decoding Instructions.cfg] måste du ta med en [!DNL DelimitedDecoder] -parameter till din anpassade fil.

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   Lägga till [!DNL DelimitedDecoder] kan du dra nytta av funktionsuppdateringar och undvika eventuella loggbearbetningsproblem som uppstår till följd av dessa uppdateringar.
