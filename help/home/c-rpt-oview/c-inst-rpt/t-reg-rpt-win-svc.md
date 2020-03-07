---
description: Steg för att registrera och köra Report Server.
solution: Analytics
title: Registrerar rapportservern som en Windows-tjänst
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Registrerar rapportservern som en Windows-tjänst{#registering-report-server-as-a-windows-service}

Steg för att registrera och köra Report Server.

Innan du utför den här proceduren måste du identifiera det Windows-konto som tjänsten ska köras under [!DNL Report Server] . Se till att det här kontot har rätt behörigheter för att komma åt den plats där genererade rapporter lagras (d.v.s. använd inte [!DNL Local System Account]).

Använd proceduren nedan för att börja [!DNL Report Server]. När du startar [!DNL Report Server] för första gången registreras den automatiskt som en Windows-tjänst.

När du startar [!DNL Report Server] för första gången ansluter programmet automatiskt till Adobe License Server för att registrera ditt digitala certifikat. Datorn måste vara ansluten till Internet när du utför följande steg för att registreringsprocessen ska slutföras.

1. I Windows navigerar du till den katalog där du installerade [!DNL Report Server].

   Exempel: D:\Adobe\Report

1. Dubbelklicka **[!UICONTROL ReportServer.exe]**.
1. Bekräfta att [!DNL Report Server] körs som det ska genom att klicka **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Kommandosekvensen kan variera beroende på vilken version av Windows du använder.
1. Leta reda på posten i tjänstlistan [!DNL Report Server] och bekräfta att dess status är Startad och att startmetoden är Automatisk.
1. Gör följande för att ange vilket användarkonto som [!DNL Report Server] ska köras:

   1. Dubbelklicka **[!UICONTROL Report Server]** för att öppna [!DNL Properties] fönstret.

   1. Klicka på **[!UICONTROL Log On]** fliken.
   1. Markera **[!UICONTROL This account]** alternativknappen.
   1. Skriv eller bläddra efter kontonamnet. Det här kontot måste ha behörighet att komma åt den plats där genererade rapporter lagras.

      >[!NOTE]
      >
      >Om [!DNL Report Server] distribuerar rapporter som Microsoft Excel-filer ( [!DNL .xls] eller [!DNL .xlsx]) måste kontot också ha behörighet att köra Microsoft Excel.

   1. Ange och bekräfta lösenordet för kontot.
   1. Klicka på **[!UICONTROL OK]**.

1. Högerklicka på [!DNL Report Server] tjänsten och välj **[!UICONTROL Restart]** att starta om tjänsten under det konto du angav.
1. Om du vill kontrollera om det [!DNL Report Server] uppstod några fel under starten klickar du på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Kommandosekvensen kan variera beroende på vilken version av Windows du använder.

   1. Välj Programloggen i den vänstra rutan i [!DNL Event Viewer] fönstret.
   1. I den högra rutan letar du efter händelser med Adobe i [!DNL Source] kolumnen.
   1. Om du hittar ett fel från Adobe dubbelklickar du på felet för att visa [!DNL Event Properties] fönstret. Det här fönstret innehåller detaljerad information om felet.

      >[!NOTE]
      >
      >När [!DNL Report Server] tjänsten har startats [!DNL ReportServer.log] skapas filen i [!DNL Trace] katalogen Report Server. Den här filen är också användbar för felsökning av problem med [!DNL Report Server].

Du har slutfört installationen av [!DNL Report Server]. [!DNL Report Server] är konstruerad för att köras kontinuerligt. Om du startar om datorn startar [!DNL Report Server] om automatiskt. Om du behöver starta och stoppa [!DNL Report Server] manuellt kan du göra det med hjälp av [!DNL Services] kontrollpanelen i Windows.
