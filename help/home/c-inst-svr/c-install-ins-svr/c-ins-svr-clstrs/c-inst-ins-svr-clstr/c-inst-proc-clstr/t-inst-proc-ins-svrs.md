---
description: En bearbetningsserver för Insight Server är identisk med en överordnad Insight Server förutom innehållet i dess komponentkatalog.
title: Installera och konfigurera Processing Insight-servrar
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# Installera och konfigurera Processing Insight-servrar{#installing-and-configuring-the-processing-insight-servers}

En bearbetningsserver för Insight Server är identisk med en överordnad Insight Server förutom innehållet i dess komponentkatalog.

Komponentkatalogen i en bearbetning [!DNL Insight Server] innehåller en speciell uppsättning filer som är specifikt konfigurerade för bearbetning [!DNL Insight Servers]. De här filerna kommer från katalogen Komponenter för bearbetning av servrar på överordnad [!DNL Insight Server].

När du installerar en bearbetning [!DNL Insight Server] gör du följande för att konfigurera komponentkatalogen:

1. Ta bort den ursprungliga komponentkatalogen på bearbetningen [!DNL Insight Server].
1. Byt namn på katalogen Komponenter för bearbetning av servrar till Komponenter.
1. Ändra [!DNL Synchronize.cfg] i komponentkatalogen så att den pekar på överordnad [!DNL Insight Server].

**Så här installerar och konfigurerar du en bearbetning[!DNL Insight Server]**

1. Installera [!DNL Insight Server]-programfilerna enligt beskrivningen i [Installera Insight Server Program Files](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Var noga med att duplicera katalogstrukturen som användes på överordnad [!DNL Insight Server]. Om till exempel [!DNL Insight Server] är installerat i [!DNL C:\Adobe\Server] på överordnad [!DNL Insight Server] måste du installera det i [!DNL C:\Adobe\Server] även på bearbetningen [!DNL Insight Servers].
1. Installera det digitala certifikatet som Adobe har utfärdat för den här bearbetningen [!DNL Insight Server]. Mer information finns i [Hämta och installera digitala certifikat](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Gör följande med Utforskaren i Windows när du bearbetar [!DNL Insight Server]:

   1. Ta bort mappen **[!UICONTROL Components]**.
   1. Byt namn på mappen [!DNL Components for Processing Servers] till Komponenter.

1. Använd en textredigerare som Anteckningar och öppna filen [!DNL Synchronize.cfg] i katalogen Components vid bearbetningen [!DNL Insight Server].
1. Lägg till IP-adressen för den överordnad (primära) [!DNL Insight Server] på den andra raden i den här filen, som i följande filfragment. Redigera ingenting annat i den här filen.

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
1. Starta [!DNL Insight Server] enligt beskrivningen i [Registrera Insight Server som en Windows-tjänst](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Du har nu slutfört installationen av ditt [!DNL Insight Server]-kluster. Konfigurera sedan datauppsättningsprofilen så att den körs i klustret enligt beskrivningen i följande avsnitt.
