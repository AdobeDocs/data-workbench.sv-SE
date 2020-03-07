---
description: Steg för att mappa rapportportalen till en virtuell katalog (IIS 5.0).
solution: Analytics
title: Mappningsrapportportal till en virtuell katalog (IIS 5.0)
topic: Data workbench
uuid: 9514c33e-c139-4cc2-97c2-8b241522c44d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappningsrapportportal till en virtuell katalog (IIS 5.0){#mapping-report-portal-to-a-virtual-directory-iis}

Steg för att mappa rapportportalen till en virtuell katalog (IIS 5.0).

1. Starta IIS-hanteraren på den dator där [!DNL Report Portal] är installerad med **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]** eller **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services]**.

1. Välj **[!UICONTROL Local Machine]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Högerklicka **[!UICONTROL Default Web Site]** och välj **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. När [!DNL Virtual Directory Wizard] fönstret öppnas klickar du på **[!UICONTROL Next]**.

1. Utför följande steg för att definiera den virtuella rotkatalogen för [!DNL Report Portal]:

   1. När du uppmanas att ange ett alias skriver du namnet på [!DNL Report Portal]och klickar sedan på **[!UICONTROL Next]**. Om du t.ex. vill använda &quot;Portal&quot; som namn på din katalog [!DNL Report Portal]tilldelar du aliaset &quot;Portal&quot; till den virtuella katalogen. Klicka **[!UICONTROL Next]** när du är klar.

   1. När du uppmanas att ange den fysiska sökvägen bläddrar du till och väljer *&lt;**[!UICONTROL PortalName]**>* - **[!UICONTROL \PortalASP]** katalogen och klickar sedan på **[!UICONTROL Next]**.

      Exempel: [!DNL C:\Inetpub\wwwroot\Portal\PortalASP]

   1. Kontrollera att följande alternativ är aktiverade när du uppmanas att ange behörigheter:

      * **[!UICONTROL Read]**
      * **[!UICONTROL Run scripts (such as ASP)]**
   1. Klicka **[!UICONTROL Next]** och sedan på **[!UICONTROL Finish]**. Den virtuella katalog som du skapade visas under standardwebbplatsen enligt följande exempel.
   ![](assets/RptPort_scrn_VirDirManual.png)

1. Högerklicka på den virtuella katalog som du just skapade och välj **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]**.

1. Använd guiden för att [!DNL Virtual Directory] skapa ett alias för var och en av följande fysiska kataloger. Då skapas en virtuell katalog med rätt namn för var och en av dessa fysiska resurser.

<table id="table_B2E04423C20F40CAA8EDA3FCBA210AA2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Skapa det här aliaset. . . </th> 
   <th colname="col2" class="entry"> För den här fysiska resursen. . . </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Core </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Core </p> <p>Exempel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Core</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CSS </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\CSS </p> <p>Exempel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\CSS</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> HTC </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\HTC </p> <p>Exempel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\HTC</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bilder </td> 
   <td colname="col2"> <p>\<i>PortalName</i>\PortalFiles\Images </p> <p>Exempel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Images</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdata </td> 
   <td colname="col2"> <p>Den fysiska platsen för den katalog där <span class="keyword"> Report Server</span> sparar utdata för rapportuppsättningarna. Utdatamappen kan finnas var som helst, ha valfritt namn och innehålla en undermapp för varje rapportuppsättning. </p> <p>Detta måste vara samma katalog som du anger i parametern Output Root i filen <span class="filepath"> Report.cfg</span> för en rapportuppsättning. Mer information finns i <a href="../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d"> Konfigurera Report.cfg-filer</a>. </p> <p>Standardplatsen är \<i>PortalName</i>\PortalFiles\Output. </p> <p>Exempel: <span class="filepath"> C:\Inetpub\wwwroot\Portal\PortalFiles\Output</span> </p> <p>Filen <i>PortalName</i>\PortalFiles\Output directory contains the <span class="filepath"> profiles.xml</span> , som måste flyttas till den utdatakatalog som du anger för det här aliaset. </p> <p>Det är viktigt att attributet <span class="wintitle"> Path</span> är korrekt inställt. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. När du är klar kontrollerar du att IIS visar sex nya virtuella kataloger. Se till att katalogstrukturen har en överordnad mapp (med samma namn som portalen) och fem undermappar som visas nedan.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. När du är klar går du till [Redigera sessionskonfigurationsfilen](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7) för att fortsätta med installationsprocessen.

