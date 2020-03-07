---
description: Följ de här stegen för att uppgradera till Data Workbench v6.4.
title: Uppgraderar 6.3 till 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Uppgraderar 6.3 till 6.4{#upgrading-to}

Följ de här stegen för att uppgradera till Data Workbench v6.4.

## Krav och rekommendationer för uppgradering {#section-8704a9ac358246cd81233dd0982d534f}

Följ dessa krav och rekommendationer när du uppgraderar till Data Workbench 6.4.

>[!IMPORTANT]
>
>Vi rekommenderar att du använder de nyinstallerade standardkonfigurationsfilerna och anpassar dem, i stället för att flytta filer från en tidigare installation, med följande undantag:

* **Lägg till** ***undantagna processer*** för *MS System Center Endpoint Protection i Windows 2012-servrar* för följande körbara filer:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Detta ger behörighet för&quot;vit lista&quot; för dessa korsande körbara filer.

* **Uppdatera certifikatet *Trust_ca_cert.pem*på servrarna**.
* **Omorganisation av attribueringsprofiler**.

   * Mappen *Attribution* döptes om till ***Attribution - Premium*** (finns i standardinstallationen på *Profiles*\*Attribution - Premium*).

   * Profilen *Premium* togs bort och arbetsytan flyttades till den nya mappen ***Attribution - Premium*** .

* **Uppdatera *Attribution-Premium*-inställningar**. Om du har anpassade profiler med parameterinställningar som åsidosätter *Adobe SC* -standardprofilen måste du uppdatera de anpassade fälten i dessa konfigurationsfiler:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* På grund av den här omorganisationen vill du ta bort de gamla mapparna *Attribution* och *Premium* från serverinstallationen.

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

* **Uppdatera anpassade Meta.cfg-filer** (om det behövs).

   Filerna **[!DNL Meta.cfg]** i **[!DNL Base\Context and AdobeSC\Context]** mapparna har uppdaterats i den här versionen.

   Om du åsidosätter **filen meta.cfg** under installationen måste din profilkopia uppdateras med de här parametrarna och **metadatavektorn** anges korrekt:

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

* **Ange behörighet** för Report Server för att skapa Microsoft Excel-rapporter på Windows 2012-servrar.

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

* **Lägg till teckensnitt i rapportservern.** Lägg till följande teckensnitt (för alla språk) i **[!DNL ReportServer.cfg]**filen:

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Uppdatera din version av Microsoft Excel **(om det behövs).

   I och med lanseringen av Data Workbench 6.4 har stödet för Excel 2007 upphört. Eftersom Data Workbench endast kan köras i Microsoft Windows med 64-bitarsarkitektur rekommenderar vi att du även installerar en 64-bitarsversion av Microsoft Excel.

* **64-bitarsarkitektur** krävs för Workstation-installation (klient).
* **Kör installationsguiden** för arbetsstationen.

   Installera den nya versionen av arbetsstationen (klienten) genom att ladda ned och starta ***InsightSetup.exe*** och stega igenom installationsanvisningarna. Installationsguiden installerar dina filer på en ny plats som standard:

   Programfiler sparas nu som standard till:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Datafiler (profiler, certifikat, spårningsloggar och användarfiler) sparas nu som standard till:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Lägg till teckensnitt i arbetsstationen**.

   Lägg till följande teckensnitt (för alla språk) i **[!DNL Insight.cfg]** filen:

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

