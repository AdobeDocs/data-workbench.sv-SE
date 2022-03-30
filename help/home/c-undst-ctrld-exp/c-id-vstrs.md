---
description: En typisk webbplatskonfiguration använder cookies för att unikt identifiera besökare på webbplatsen och spåra deras beteende över tid.
solution: Analytics
title: Hur identifierar webbplatsen besökare?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---

# Hur identifierar webbplatsen besökare?{#how-does-site-identify-visitors}

En typisk webbplatskonfiguration använder cookies för att unikt identifiera besökare på webbplatsen och spåra deras beteende över tid.

Första gången en viss webbläsare (betraktas som besökare) begär din webbplats, [!DNL Sensor] fungerar med webbservern för att ange en beständig cookie (som standard [!DNL cs(cookie)(v1st)]), som tolkas internt i systemet som [!DNL x-trackingid]. Den här cookie-filen anges endast en gång på den allra första begäran som besökaren gjort till webbplatsen. Den samlas sedan in från besökaren varje gång webbläsaren gör en begäran (antingen sida eller inbäddade objektbegäranden) om webbplatsen i framtiden.

Det är webbläsaren som bestämmer om en beständig cookie ska godkännas. Om en användare väljer att blockera beständiga cookies loggas fortfarande deras sidvisningsbegäranden, men mätdata från dessa begäranden korreleras inte med en viss besökare eller deras sessioner på webbplatsen om du inte implementerar en alternativ metod för besökaridentifiering, som att använda Hash-omvandling i fälten IP och UserAgent.

>[!NOTE]
>
>Webbplatsexperiment kan bara analyseras i datauppsättningar där den enda metod för besöksidentifiering som används är [!DNL Sensor] ange beständig cookie-metod. Sensorer som körs på J2EE-servrar (JBoss, Tomcat, WebLogic och WebSphere) stöder inte kontrollerade experiment.

Under ett kontrollerat experiment kan användare som inte accepterar cookies placeras i olika experimentgrupper från ett klick till nästa. Detta blir bara ett problem om du utför din testanalys med filtret för bruten session inaktiverat i [!DNL Insight], vilket Adobe inte rekommenderar.

Mer information om filtret för bruten session finns i * [!DNL Insight] Användarhandbok*.

Om en besökare rensar cookien under ett experiment tilldelas besökaren en ny cookie som kan tilldelas en annan grupp. Eftersom Adobe identifierar besökaren som ny blir experimentet inte ogiltigt.
