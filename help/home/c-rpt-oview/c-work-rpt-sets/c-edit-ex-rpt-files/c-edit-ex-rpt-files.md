---
description: Steg för att redigera befintliga Report.cfg-filer med hjälp av Worker eller en textredigerare.
solution: Analytics
title: Redigera befintliga Report.cfg-filer
topic: Data workbench
uuid: 494b9eef-42f3-4ed9-8b43-f5c09af33f2e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Redigera befintliga Report.cfg-filer{#editing-existing-report-cfg-files}

Steg för att redigera befintliga Report.cfg-filer med hjälp av Worker eller en textredigerare.

>[!NOTE]
>
>* Du måste arbeta online för att redigera [!DNL Report.cfg] filer. Om du vill arbeta online [!DNL Worktop]högerklickar du på namnlisten och klickar på **[!UICONTROL Work Online]**.
   >
   >
* Om **[!UICONTROL Allow Report Regeneration]** parametern i [!DNL Report.cfg] filen är inställd på [!DNL True][!DNL Report] återskapas rapporterna i den uppsättningen automatiskt när du gör ändringar i filen och sparar filen på servern. Rapporterna genereras om, men de skickas inte om via e-post. Anvisningar om hur du gör det finns i [Skicka rapporter via e-post](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/t-res-rpts-email.md#task-b0a21f1c925f4e5d82560581ae4cf607).
>



Du kan redigera en befintlig [!DNL Report.cfg] från [!DNL Worktop] eller med en textredigerare.

Om du redigerar en [!DNL Report.cfg] fil med hjälp av [!DNL Reports] fliken på [!DNL Worktop] kan du bara redigera de parametrar, vektorer och vektorobjekt som redan finns i filen. Om du behöver lägga till en parameter eller vektor i filen måste du redigera den med en textredigerare, till exempel Anteckningar.

* [Så här redigerar du en befintlig Report.cfg med hjälp av arbetsytan](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-7bce3bca006149c79be7678430f21945)
* [Redigera en befintlig Report.cfg med en textredigerare](../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#section-06f3d2a8d7f34bc2841180caf10a1eb7)

## Så här redigerar du en befintlig Report.cfg med hjälp av arbetsytan {#section-7bce3bca006149c79be7678430f21945}

>[!NOTE]
>
>Du måste arbeta online för att kunna redigera [!DNL Report.cfg] från [!DNL Worktop].

1. På fliken [!DNL Reports] Data Workbench väljer du undermappen (flik eller nedrullningsbar underkatalog) för den rapportuppsättning som du vill konfigurera.
1. Klicka på **[!UICONTROL Report.cfg]**. Parametrarna för [!DNL Report.cfg] rapportuppsättningen visas.

1. Redigera konfigurationsparametrarna efter behov. Mer information om de här parametrarna finns i [Report.cfg-parametrar](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Spara filen genom att högerklicka **[!UICONTROL Report.cfg (modified)]** överst i parametrarna och klicka på **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.

## Redigera en befintlig Report.cfg med en textredigerare {#section-06f3d2a8d7f34bc2841180caf10a1eb7}

1. Öppna [!DNL Reports Manager] genom att högerklicka på en arbetsyta och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Reports Manager]**.

1. Klicka på mappen för din rapportuppsättning.
1. Högerklicka på bockmarkeringen bredvid [!DNL Report.cfg] för den här rapportuppsättningen och klicka på **[!UICONTROL Make Local]**.

1. Högerklicka på bockmarkeringen bredvid [!DNL User] för den här rapportuppsättningen i [!DNL Report.cfg] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Filen [!DNL Report.cfg] öppnas.

   Exemplet [!DNL Report.cfg] som visas i [Konfigurera rapportuppsättningen](../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) innehåller som standard bara de parametrar som finns i [!DNL Report.cfg] filen. I följande exempel finns alla parametrar som är tillgängliga för filen och som du kan använda som modeller för dina parameterposter: [!DNL Report.cfg]

   ```
   Attachments = vector: 1 items
     0 = Attachment:
       FileName = string: c:\\myimage.jpg
       Content Type = string: image/jpeg
   Alert Threshold = int: 0
   Allow Report Regeneration = bool: true
   Color Set = int: 1
   Command To Execute = string: 
   Default Excel Template = string: 
   Dimension Name = string: 
   Email Only If Perfect = bool: false
   End Date = string: 
   Every = string: month
   Excel Watchdog Timeout (seconds) = double: 300.0
   Filter Formula = string: 
   Gamma Correction = double: 1
   Hide Logos = bool: false
   Lookup File = string: 
   Mail Report = MailReport: 
     Body XSL Template = string: 
     Recipients = vector: 0 items
     SMTP Server = SmtpServerInfo: 
       Address = string: 
       Password = string: 
       User = string: 
     Sender Address = string: 
     Sender Name = string: 
     Subject = string: 
   Notification Only = bool: false
   Output Root = string: 
   Report Types = vector: 3 items
     0 = string: thumbnail
     1 = string: png
     2 = string: excel
   Start Date = string: 7/1/06 19:16 EDT
   Thumbnail X = int: 240
   Thumbnail Y = int: 180
   Top N Metric = string: 
   Top N Value = int: 0
   Use Local Sample Only = bool: false
   Workspace Path = string: 
   ```

1. Redigera konfigurationsparametrarna efter behov. Mer information om de här parametrarna finns i [Report.cfg-parametrar](../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
1. Spara och stäng filen.
1. I [!DNL Reports Manager]högerklickar du på bockmarkeringen i [!DNL User] kolumnen för [!DNL Report.cfg] filen och väljer **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.

