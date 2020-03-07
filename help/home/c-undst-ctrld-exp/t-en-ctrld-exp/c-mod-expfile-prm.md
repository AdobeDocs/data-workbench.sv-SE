---
description: ExpFile-parametern pekar på platsen för experimentets konfigurationsfil, som definierar ditt experiment.
solution: Insight,Analytics
title: Ändra parametern ExpFile
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ändra parametern ExpFile{#modifying-the-expfile-parameter}

ExpFile-parametern pekar på platsen för experimentets konfigurationsfil, som definierar ditt experiment.

Om du ställer in den här parametern kan du köra experiment. Anvisningar om hur du skapar konfigurationsfilen för experimentet finns i [Konfigurera och distribuera experimentversionen](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Här följer ett exempel på parametern ExpFile:

```
ExpFile /home/experiment.txt
```

Den här tabbavgränsade textfilen ( [!DNL .txt]) kan finnas var som helst i [!DNL Sensor] mappen och kan ha vilket bekvämt namn som helst.

Se till att du registrerar platsen för katalogen med experiment och namnet på konfigurationsfilen som du anger eftersom du måste spara konfigurationsfilen för experimentet (som beskrivs senare i den här guiden) med det här namnet och i den här katalogen.

>[!NOTE]
>
>Om du inte anger den här parametern på samma sätt på alla datorer i webbklustret som en [!DNL Sensor] är installerad på fungerar inte kontrollerade försök.

Den här posten kan förkonfigureras och finnas kvar i konfigurationsfilen på [!DNL Sensor] kontinuerlig basis utan någon negativ effekt. Om det angivna namnet på experimentkonfigurationsfilen inte hittas av [!DNL Sensor] eller är tomt (d.v.s. finns, men inte har något innehåll) loggar [!DNL Sensor] inte experimentet, loggar en felhändelse på HTTP-servern och fortsätter att fungera som vanligt i alla andra avseenden.