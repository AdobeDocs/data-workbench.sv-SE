---
description: En bearbetningsserver för Insight Server är identisk med en huvudserver för Insight, förutom innehållet i dess komponentkatalog.
solution: Insight
title: Installera och konfigurera Processing Insight-servrar
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installera och konfigurera Processing Insight-servrar{#installing-and-configuring-the-processing-insight-servers}

En bearbetningsserver för Insight Server är identisk med en huvudserver för Insight, förutom innehållet i dess komponentkatalog.

Komponentkatalogen i en bearbetning [!DNL Insight Server] innehåller en särskild uppsättning filer som är särskilt konfigurerade för bearbetning [!DNL Insight Servers]. De här filerna kommer från katalogen Komponenter för bearbetning av servrar på huvudservern [!DNL Insight Server].

När du installerar en bearbetning [!DNL Insight Server]gör du följande för att konfigurera komponentkatalogen:

1. Ta bort den ursprungliga komponentkatalogen i bearbetningen [!DNL Insight Server].
1. Byt namn på katalogen Komponenter för bearbetning av servrar till Komponenter.
1. Ändra inställningarna [!DNL Synchronize.cfg] i komponentkatalogen så att de pekar på mallsidan [!DNL Insight Server].

**Så här installerar och konfigurerar du en bearbetning[!DNL Insight Server]**

1. Installera [!DNL Insight Server] programfilerna enligt beskrivningen i [Installera Insight Server Program Files](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Var noga med att duplicera katalogstrukturen som användes på mallsidan [!DNL Insight Server]. Om [!DNL Insight Server] till exempel är installerat i [!DNL C:\Adobe\Server] mallen [!DNL Insight Server]måste du installera det [!DNL C:\Adobe\Server] i bearbetningen [!DNL Insight Servers] också.
1. Installera det digitala certifikatet som Adobe har utfärdat för just den här bearbetningen [!DNL Insight Server]. Mer information finns i [Hämta och installera digitala certifikat](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) .
1. Gör följande i Utforskaren i Windows [!DNL Insight Server]:

   1. Ta bort **[!UICONTROL Components]** mappen.
   1. Byt namn på [!DNL Components for Processing Servers] mappen till Komponenter.

1. Använd en textredigerare som Anteckningar för att öppna filen i katalogen Komponenter i bearbetningen [!DNL Synchronize.cfg] [!DNL Insight Server].
1. Lägg till huvudfilens IP-adress (primär) [!DNL Insight Server] till den andra raden i den här filen enligt följande filfragment. Redigera ingenting annat i den här filen.

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. Spara filen.
1. Starta programmet [!DNL Insight Server] enligt beskrivningen i [Registrera Insight Server som en Windows-tjänst](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Du har nu slutfört installationen av ditt [!DNL Insight Server] kluster. Konfigurera sedan datauppsättningsprofilen så att den körs i klustret enligt beskrivningen i följande avsnitt.

