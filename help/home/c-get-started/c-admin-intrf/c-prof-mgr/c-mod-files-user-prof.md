---
description: Du kan använda Profilhanteraren för att hämta filer som du vill ändra.
title: Ändra lokala filer i användarprofilen
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 0%

---

# Ändra lokala filer i användarprofilen{#modify-local-files-in-the-user-profile}

{{eol}}

Du kan använda Profilhanteraren för att hämta filer som du vill ändra.

Du kanske vill ladda ned en fil som skriver över din befintliga lokala fil med den ursprungliga versionen av filen eller öppna, visa och ändra filer som inte går att komma åt på arbetsytans menyer.

**Så här hämtar du en fil**

1. I [!DNL Profile Manager]öppnar du de mappar och undermappar som behövs för att hitta filen som du vill hämta.
1. Högerklicka på bockmarkeringen bredvid filens namn och klicka på **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Konfiguration ( [!DNL .cfg]), dimension ( [!DNL .dim]), och mätvärden ( [!DNL .metric]) kan redigeras direkt i en profilmapp och sparas på servern utan att göra dem lokala och spara dem separat på servern. Högerklicka bara på bockmarkeringen bredvid filens namn och klicka på **[!UICONTROL Open]** > **i arbetsstationen**.

När filen har laddats ned till den lokala datorn visas en bock i [!DNL User] -kolumnen, som anger att en lokal kopia av filen finns i mappen User\*profile name* på datorn. Observera att bockmarkeringen har samma färg som bockmarkeringen i *profilnamn* kolumn. Detta anger att den lokala filen har samma ändringsdatum och -tid som filen i *profilnamn* mapp.

**Ändra filen**

1. Högerklicka på bockmarkeringen bredvid filnamnet i dialogrutan [!DNL User] kolumn.
1. Klicka på något av följande menyalternativ, beroende på hur du vill redigera filen:

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** om du redigerar en [!DNL .vw] eller en [!DNL .cfg] i en arbetsyta.

   * **Öppna** > **in vw. Redigeraren **om du redigerar en VW-fil för att lägga till nya parametrar.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** om du öppnar en textfil eller behöver lägga till nya parametrar i en [!DNL .cfg] -fil.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** om du vill öppna mappen där filen finns på datorn

1. Redigera filen efter behov och spara sedan filen.

I [!DNL Profile Manager], observera att bockmarkeringen finns i [!DNL User] -kolumnen för filen som du redigerade har ändrat färg. Detta anger att den lokala filen nu skiljer sig från versionen i *profilnamn* mapp. Om det behövs kan du publicera den reviderade versionen av filen i profilen så att andra användare som arbetar med profilen kan använda den.
