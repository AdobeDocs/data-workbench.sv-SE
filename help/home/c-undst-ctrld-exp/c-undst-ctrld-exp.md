---
description: Kontrollerade försök är tester som gör att du kan jämföra resultat från en experimentell exempelgrupp med resultat från en standardkontrollgrupp.
solution: Analytics
title: Experimentera med Data Workbench
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Experimentera med Data Workbench{#data-workbench-controlled-experiments}

Kontrollerade försök är tester som gör att du kan jämföra resultat från en experimentell exempelgrupp med resultat från en standardkontrollgrupp.

På webbplatsen kan du implementera, mäta och analysera kontrollerade experiment och deras resultat när de relaterar till olika aspekter av webbplatsen. På så sätt kan du testa hypoteser om hur webbplatsen kan förbättras innan du lägger mycket tid eller pengar på att helt genomföra de föreslagna ändringarna.

>[!NOTE]
>
>Webbplatsexperiment kan bara analyseras i datauppsättningar där den enda metod för besöksidentifiering som används är [!DNL Sensor] ange beständig cookie-metod. Sensorer som körs på J2EE-servrar (JBoss, Tomcat, WebLogic och WebSphere) stöder inte kontrollerade experiment. Mer information finns i följande avsnitt.

Med Site kan man implementera A/B, A/B/A och multivariata kontrollerade experiment för att samla in tillräckligt med testdata för att få statistiskt korrekta data för en detaljerad utvärdering av hypotesen, utan att det påverkar webbplatsens prestanda.
