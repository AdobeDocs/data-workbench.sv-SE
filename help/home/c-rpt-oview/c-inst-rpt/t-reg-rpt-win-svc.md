---
description: Steg för att registrera och köra Report Server.
title: Registrerar rapportservern som en Windows-tjänst
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Registrerar rapportservern som en Windows-tjänst{#registering-report-server-as-a-windows-service}

{{eol}}

Steg för att registrera och köra Report Server.

Innan du utför den här proceduren måste du identifiera det Windows-konto som [!DNL Report Server] kommer att köras. Kontrollera att kontot har rätt behörighet att komma åt den plats där genererade rapporter lagras (d.v.s. använd inte [!DNL Local System Account]).

Använd proceduren nedan för att börja [!DNL Report Server]. När du börjar [!DNL Report Server] För första gången registreras den automatiskt som en Windows-tjänst.

När du börjar [!DNL Report Server] För första gången ansluter programmet automatiskt till Adobe License Server för att registrera ditt digitala certifikat. Datorn måste vara ansluten till Internet när du utför följande steg för att registreringsprocessen ska slutföras.

1. I Windows går du till den katalog där du installerade [!DNL Report Server].

   Exempel: D:\Adobe\Report

1. Dubbelklicka **[!UICONTROL ReportServer.exe]**.
1. Bekräfta att [!DNL Report Server] körs korrekt, klicka **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Kommandosekvensen kan variera beroende på vilken version av Windows du använder.
1. Leta reda på posten för [!DNL Report Server] och bekräfta att dess status är Startad och att startmetoden är Automatisk.
1. Gör följande för att ange vilket användarkonto som [!DNL Report Server] kommer att köras:

   1. Dubbelklicka **[!UICONTROL Report Server]** för att öppna [!DNL Properties] -fönstret.

   1. Välj **[!UICONTROL Log On]** -fliken.
   1. Välj **[!UICONTROL This account]** alternativknapp.
   1. Skriv eller bläddra efter kontonamnet. Det här kontot måste ha behörighet att komma åt den plats där genererade rapporter lagras.

      >[!NOTE]
      >
      >If [!DNL Report Server] distribuerar rapporter som Microsoft Excel ( [!DNL .xls] eller [!DNL .xlsx]) ska du kontrollera att kontot även har behörighet att köra Microsoft Excel.

   1. Ange och bekräfta lösenordet för kontot.
   1. Klicka på **[!UICONTROL OK]**.

1. Högerklicka på [!DNL Report Server] service och välj **[!UICONTROL Restart]** för att starta om tjänsten under det angivna kontot.
1. Kontrollera om [!DNL Report Server] har råkat ut för fel under starten, klicka **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Kommandosekvensen kan variera beroende på vilken version av Windows du använder.

   1. I den vänstra rutan i [!DNL Event Viewer] väljer du programloggen.
   1. I den högra rutan letar du efter händelser med Adobe i [!DNL Source] kolumn.
   1. Om du hittar ett fel från Adobe dubbelklickar du på felet för att visa [!DNL Event Properties] -fönstret. Det här fönstret innehåller detaljerad information om felet.

      >[!NOTE]
      >
      >Efter [!DNL Report Server] startar filen [!DNL ReportServer.log] skapas i rapportservern [!DNL Trace] katalog. Den här filen är också användbar vid felsökning av problem med [!DNL Report Server].

Du har slutfört installationen av [!DNL Report Server]. [!DNL Report Server] är konstruerad för att köras kontinuerligt. Om du startar om datorn [!DNL Report Server] startar om automatiskt. Om du behöver starta och stoppa [!DNL Report Server] manuellt kan du göra det med [!DNL Services] Kontrollpanelen i Windows.
