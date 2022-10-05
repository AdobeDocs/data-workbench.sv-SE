---
description: Följ de här stegen för att uppgradera till Data Workbench v6.4.
title: Uppgraderar 6.3 till 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
exl-id: 540deb86-2463-4820-b67a-a32d68b4346e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Uppgraderar 6.3 till 6.4{#upgrading-to}

{{eol}}

Följ de här stegen för att uppgradera till Data Workbench v6.4.

## Uppgraderingskrav och Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Följ dessa krav och rekommendationer när du uppgraderar till Data Workbench 6.4.

>[!IMPORTANT]
>
>Vi rekommenderar att du använder de nyinstallerade standardkonfigurationsfilerna och anpassar dem, i stället för att flytta filer från en tidigare installation, med följande undantag:

* **Lägg till** ***Exkluderade processer*** for *MS System Center Endpoint Protection i Windows 2012-servrar* för följande körbara filer:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Detta aktiverar tillåtelselista-rättigheter för dessa korsande körbara filer.

* **Uppdatera *Trust_ca_cert.pem* certifikat på servrarna**.
* **Omorganisation av attribueringsprofiler**.

   * The *Attribut* mappen har bytt namn till ***Attribution - Premium*** (finns i standardinstallationen på *Profiler*\*Attribution - Premium*).

   * The *Premium* profilen togs bort och arbetsytan flyttades till den nya ***Attribution - Premium*** mapp.

* **Uppdatera *Attribution-Premium* inställningar**. Om du har anpassade profiler med parameterinställningar som åsidosätter standardinställningarna *Adobe SC* måste du uppdatera de anpassade fälten i dessa konfigurationsfiler:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* På grund av den här omorganisationen vill du ta bort den gamla *Attribut* och *Premium* mappar från serverinstallationen.

   **Ändra de här inställningarna**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   till dessa inställningar:

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **Uppdatera anpassade Meta.cfg-filer** (vid behov).

   The **[!DNL Meta.cfg]** filer i **[!DNL Base\Context and AdobeSC\Context]** mappar har uppdaterats i den här versionen.

   Om du åsidosätter **meta.cfg** under installationen måste din profilkopia uppdateras med de här parametrarna och **metadatavektor** lämpligt angivet:

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* **Ange behörigheter för rapportservern** för att generera Microsoft Excel-rapporter på Windows 2012-servrar.

   1. Ange behörighet för rotmappen (**[!DNL E:\ReportServer\]**) till *Alla = full kontroll*.

   1. Skapa följande mappar med lämplig behörighet:

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Om du kör Report Server på Windows Server 2012 måste du ha Windows Server 2012 R2 installerat.

   1. Tilldela &quot;SYSTEM&quot; som ägare för dessa mappar.

* **Lägg till teckensnitt i rapportservern.** I[!DNL ReportServer.cfg]**file, add these fonts (for all languages):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Uppdatera din version av Microsoft Excel **(om det behövs).

   I och med Data Workbench 6.4 har stödet för Excel 2007 upphört. Eftersom Data Workbench endast kan köras i Microsoft Windows med 64-bitarsarkitektur rekommenderar vi att du också installerar en 64-bitarsversion av Microsoft Excel.

* **64-bitarsarkitektur** krävs för installation av arbetsstation (klient).
* **Kör installationsguiden för arbetsstationen**.

   Installera den nya versionen av arbetsstationen (klienten) genom att hämta och starta ***InsightSetup.exe*** och stega igenom instruktionerna. Installationsguiden installerar dina filer på en ny plats som standard:

   Programfiler sparas nu som standard till:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Datafiler (profiler, certifikat, spårningsloggar och användarfiler) sparas nu som standard till:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Lägga till teckensnitt i arbetsstationen**.

   I **[!DNL Insight.cfg]** lägger du till följande teckensnitt (för alla språk):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```
