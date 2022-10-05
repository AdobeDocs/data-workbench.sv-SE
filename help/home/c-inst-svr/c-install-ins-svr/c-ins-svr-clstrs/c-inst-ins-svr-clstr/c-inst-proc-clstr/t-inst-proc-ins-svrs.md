---
description: En bearbetningsserver för Insight Server är identisk med en överordnad Insight Server förutom innehållet i dess komponentkatalog.
title: Installera och konfigurera Processing Insight-servrar
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# Installera och konfigurera Processing Insight-servrar{#installing-and-configuring-the-processing-insight-servers}

{{eol}}

En bearbetningsserver för Insight Server är identisk med en överordnad Insight Server förutom innehållet i dess komponentkatalog.

Komponentkatalogen i en bearbetning [!DNL Insight Server] innehåller en särskild uppsättning filer som är särskilt konfigurerade för bearbetning [!DNL Insight Servers]. De här filerna kommer från katalogen Components for Processing Servers på överordnad [!DNL Insight Server].

När du installerar en bearbetning [!DNL Insight Server]gör du följande för att konfigurera komponentkatalogen:

1. Ta bort den ursprungliga komponentkatalogen vid bearbetningen [!DNL Insight Server].
1. Byt namn på katalogen Komponenter för bearbetning av servrar till Komponenter.
1. Ändra [!DNL Synchronize.cfg] i Components-katalogen för att peka på överordnad [!DNL Insight Server].

**Så här installerar och konfigurerar du en bearbetning[!DNL Insight Server]**

1. Installera [!DNL Insight Server] programfiler enligt [Installera Insight Server Program Files](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Var noga med att duplicera katalogstrukturen som användes på överordnad [!DNL Insight Server]. Om [!DNL Insight Server] är installerat i [!DNL C:\Adobe\Server] på överordnad [!DNL Insight Server]måste du installera det i [!DNL C:\Adobe\Server] om bearbetningen [!DNL Insight Servers] också.
1. Installera det digitala certifikatet som Adobe har utfärdat för den här bearbetningen [!DNL Insight Server]. Se [Hämta och installera digitala certifikat](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) för instruktioner.
1. Gör följande med Utforskaren i Windows: [!DNL Insight Server]:

   1. Ta bort **[!UICONTROL Components]** mapp.
   1. Byt namn på [!DNL Components for Processing Servers] mapp till komponenter.

1. Använd en textredigerare som Anteckningar för att öppna [!DNL Synchronize.cfg] i komponentkatalogen vid bearbetningen [!DNL Insight Server].
1. Lägg till IP-adressen för överordnad (primär) [!DNL Insight Server] till den andra raden i den här filen, som i följande filfragment. Redigera ingenting annat i den här filen.

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
1. Starta [!DNL Insight Server] enligt beskrivning i [Registrerar Insight Server som en Windows-tjänst](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Du har nu slutfört installationen av [!DNL Insight Server] kluster. Konfigurera sedan datauppsättningsprofilen så att den körs i klustret enligt beskrivningen i följande avsnitt.
