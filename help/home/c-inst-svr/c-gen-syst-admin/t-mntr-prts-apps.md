---
description: Om du vill övervaka implementeringen mer noggrant kan du övervaka alla portar på serverdatorerna samt de programvaruprodukter som körs på var och en av dessa portar.
solution: Analytics
title: Övervaka portar och program
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---


# Övervaka portar och program{#monitoring-ports-and-applications}

Om du vill övervaka implementeringen mer noggrant kan du övervaka alla portar på serverdatorerna samt de programvaruprodukter som körs på var och en av dessa portar.

**Rekommenderad frekvens:** Var 5-10:e minut

Med ett program eller skript kan du övervaka den TCP-port som varje program körs på (vanligtvis port 80 eller 443) för att se till att programmet är bundet till den porten. Om du vill göra det begär du en programstatussida från datorn som du vill övervaka.

**Så här begär du statussidan för programmet**

1. Ändra åtkomstkontrollerna på den dator som du vill övervaka så att övervakningsprogrammet eller skriptet kan komma åt datorn. Instruktioner finns i [Konfigurera åtkomstkontroll](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Anslut till [!DNL https://IP Address/Status/], där IP-adressen är IP-adressen för datorn som du vill få status för.

   Exempel: [!DNL https://127.0.0.1/Status/]

   Datorn ska svara med en serverstatusbeskrivning. Om du inte svarar kan du kontrollera händelseloggarna och kontakta Adobe kundtjänst.

   Mer information om den här typen av avancerad övervakning finns hos Adobe Consulting Services.

