---
description: ExpFile-parametern pekar på platsen för experimentets konfigurationsfil, som definierar ditt experiment.
solution: Analytics
title: Ändra parametern ExpFile
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Ändra parametern ExpFile{#modifying-the-expfile-parameter}

{{eol}}

ExpFile-parametern pekar på platsen för experimentets konfigurationsfil, som definierar ditt experiment.

Om du ställer in den här parametern kan du köra experiment. Anvisningar om hur du skapar konfigurationsfilen för experimentet finns i [Konfigurera och distribuera experimentet](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Här följer ett exempel på parametern ExpFile:

```
ExpFile /home/experiment.txt
```

Den här tabbavgränsade textfilen ( [!DNL .txt]) kan finnas var som helst i [!DNL Sensor] och kan ha vilket namn som helst.

Se till att du registrerar platsen för katalogen med experiment och namnet på konfigurationsfilen som du anger eftersom du måste spara konfigurationsfilen för experimentet (som beskrivs senare i den här guiden) med det här namnet och i den här katalogen.

>[!NOTE]
>
>Om du inte anger den här parametern på samma sätt på alla datorer i webbklustret där en [!DNL Sensor] är installerat fungerar inte kontrollerade försök.

Den här posten kan förkonfigureras och finnas kvar i [!DNL Sensor] konfigurationsfilen fortlöpande utan skadlig påverkan. Om det angivna namnet på experimentkonfigurationsfilen inte hittas av [!DNL Sensor] eller så är den tom (d.v.s. den finns men har inget innehåll), [!DNL Sensor] utför inte experimentet, loggar en felhändelse på HTTP-servern och fortsätter att fungera normalt i alla andra avseenden.
