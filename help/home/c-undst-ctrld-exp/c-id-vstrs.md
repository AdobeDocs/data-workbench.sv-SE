---
description: En typisk webbplatskonfiguration använder cookies för att unikt identifiera besökare på webbplatsen och spåra deras beteende över tid.
solution: Insight,Analytics
title: Hur identifierar webbplatsen besökare?
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hur identifierar webbplatsen besökare?{#how-does-site-identify-visitors}

En typisk webbplatskonfiguration använder cookies för att unikt identifiera besökare på webbplatsen och spåra deras beteende över tid.

Första gången en viss webbläsare (som betraktas som besökare) gör en begäran på din webbplats, fungerar tillsammans med din webbserver för att ange en beständig cookie (som standard [!DNL Sensor] ), som tolkas internt i systemet som [!DNL cs(cookie)(v1st)][!DNL x-trackingid]. Den här cookie-filen anges endast en gång på den allra första begäran som besökaren gjort till webbplatsen. Den samlas sedan in från besökaren varje gång webbläsaren gör en begäran (antingen sida eller inbäddade objektbegäranden) om webbplatsen i framtiden.

Det är webbläsaren som bestämmer om en beständig cookie ska godkännas. Om en användare väljer att blockera beständiga cookies loggas fortfarande deras sidvisningsbegäranden, men mätdata från dessa begäranden korreleras inte med en viss besökare eller deras sessioner på webbplatsen om du inte implementerar en alternativ metod för besökaridentifiering, som att använda Hash-omvandling i fälten IP och UserAgent.

>[!NOTE]
>
>Webbplatsexperiment kan bara analyseras i datauppsättningar där den enda metod för identifiering av besökare som används är den [!DNL Sensor] set-beständiga cookie-metoden. Sensorer som körs på J2EE-servrar (JBoss, Tomcat, WebLogic och WebSphere) stöder inte kontrollerade experiment.

Under ett kontrollerat experiment kan användare som inte accepterar cookies placeras i olika experimentgrupper från ett klick till nästa. Detta blir bara ett problem om du utför din testanalys med filtret för bruten session inaktiverat i [!DNL Insight], vilket Adobe inte rekommenderar.

Mer information om det brutna sessionsfiltret finns i * [!DNL Insight] Användarhandbok*.

Om en besökare rensar cookien under ett experiment tilldelas besökaren en ny cookie som kan tilldelas en annan grupp. Eftersom Adobe identifierar besökaren som ny blir experimentet inte ogiltigt.
