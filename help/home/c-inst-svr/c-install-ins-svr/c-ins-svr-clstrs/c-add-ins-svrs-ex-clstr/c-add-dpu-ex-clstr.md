---
description: Vanligtvis vill du lägga till en Insight Server DPU i ett befintligt kluster när mängden data som du vill bearbeta och göra tillgänglig för dina användare av Insight och Report överskrider kapaciteten för klustrets aktuella konfiguration.
solution: Analytics
title: Lägga till en Insight Server DPU i ett befintligt kluster
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---


# Lägga till en Insight Server DPU i ett befintligt kluster{#adding-an-insight-server-dpu-to-an-existing-cluster}

Vanligtvis vill du lägga till en Insight Server DPU i ett befintligt kluster när mängden data som du vill bearbeta och göra tillgänglig för dina användare av Insight och Report överskrider kapaciteten för klustrets aktuella konfiguration.

## Uppdaterar konfigurationsfilerna på den Överordnad servern {#section-7c9a23754a994d73b722d53f999f0e82}

I [!DNL Insight]öppnar du [!DNL Server Files Manager] filen för din överordnad [!DNL Insight Server] (vanligtvis en [!DNL Insight Server] FSU) och gör följande för varje DPU som du vill lägga till i klustret:

1. Redigera adressfilen på överordnad [!DNL Insight Server] för att inkludera namn och adress för den nya DPU:n enligt beskrivningen i [Lägga till bearbetningsinsiktsservrar i adressfilen](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Lägg till namnet och adressen för den nya DPU:n i den grupp där klustrets aktuella [!DNL Insight Servers] listas.

1. Redigera åtkomstkontrollsfilen på överordnad [!DNL Insight Server] så att den innehåller IP-adressen för den nya DPU:n enligt beskrivningen i [Uppdatera åtkomstkontrollsfilen för ett kluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installera nya Insight Server DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Den här aktiviteten gäller endast för 32-bitars Windows.

1. Kopiera följande kataloger från en av de aktuella DPU:erna i klustret till den nya DPU:n:

   * [!DNL Insight Server] installationskatalog/
   * [!DNL Insight Server] installationskatalog/certifikat/
   * [!DNL Insight Server] installationskatalog/komponenter/

1. Hämta och installera det digitala certifikatet för den nya DPU enligt beskrivningen i [Hämta och installera digitala certifikat](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Ange parametrar för minnesanvändning i Windows på den nya DPU:n.
1. Registrera dig [!DNL Insight Server] som en Windows-tjänst på den nya DPU-datorn enligt beskrivningen i [Registrera Insight Server som en Windows-tjänst](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Kontrollera spårningsloggarna för att se till att DPU synkroniseras med överordnad [!DNL Insight Server].
1. Upprepa steg 1 till 6 för varje ytterligare DPU som du lägger till i klustret.

## Lägga till DPU:n för nya Insight Server i datauppsättningsprofilens bearbetningsservrar {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Om den nya DPU-processorn bearbetar samma datauppsättning som de andra DPU-enheterna i klustret lägger du till det nya DPU-filens vanliga namn i den [!DNL profile.cfg] överordnad filen [!DNL Insight Server] enligt beskrivningen i [Ange bearbetningsservrarna i Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
