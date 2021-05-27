---
description: Instruktioner för att installera och konfigurera en Insight Server FSU för användning med Repeater.
title: Konfigurera en Insight Server FSU för Repeater
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Konfigurera en Insight Server FSU för Repeater{#configuring-an-insight-server-fsu-for-repeater}

Instruktioner för att installera och konfigurera en Insight Server FSU för användning med Repeater.

Utför följande uppgifter i rätt ordning. Alla undantag eller ändringar som du måste göra så att FSU:n [!DNL Insight Server] kan användas som en upprepande server noteras efter varje steg.

1. Installera [!DNL Insight Server]-programfilerna enligt beskrivningen i [Installera Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Eftersom datorn där du installerar de här filerna används för att köra Repeater är det bra att ge installationskatalogen ett beskrivande namn, till exempel [!DNL D:\Adobe\Repeater].

1. Installera det digitala [!DNL Insight Server]-certifikatet enligt beskrivningen i [Hämta och installera digitala certifikat](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   När du har loggat in på Adobe licensserver måste du komma ihåg att söka efter certifikatnamnet som matchar serverns vanliga namn på den angivna upprepade datorn.

1. Kontrollera portinställningarna i filen [!DNL Communications.cfg] enligt beskrivningen i [Kontrollera portinställningarna](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   Om de tilldelade portarna (port och SSL-port) används av en annan process som körs på samma dator, måste du ändra porttilldelningarna till ett oanvänt par.

1. Om det behövs ändrar du loggkatalogen för de [!DNL Sensor]-data som ska samlas in och lagras på den här datorn. Instruktioner finns i [Övervaka händelsens datautrymme](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Ändra [!DNL Access Control.cfg]-filen så att den tillåter administrativ åtkomst till [!DNL Insight Server] från [!DNL Insight] enligt beskrivningen i [Uppdatera åtkomstkontrollsfilen](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Ändra [!DNL server.address]-filen för att definiera serverns nätverksplats enligt definitionen i [Definiera serverns nätverksplats](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Ange parametrar för minnesanvändning i Windows.
1. Registrera [!DNL Insight Server] som en Windows-tjänst enligt beskrivningen i [Registrera Insight Server som en Windows-tjänst](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
