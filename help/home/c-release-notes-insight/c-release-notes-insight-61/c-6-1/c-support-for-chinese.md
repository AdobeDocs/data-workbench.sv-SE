---
description: Klientprogrammet data workbench har nu stöd för förenklad kinesiska.
title: Förenklad kinesisk lokalisering
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 0%

---


# Förenklad kinesiska-lokalisering{#simplified-chinese-localization}

Klientprogrammet data workbench har nu stöd för förenklad kinesiska.

**Så här installerar du förenklad kinesiska**:

Innan du konfigurerar [!DNL Insight.exe] och stödfiler måste du avsluta klientprogrammet.

1. Skapa ett kortkommando som skickas i kommandoradsinställningen till [!DNL insight.exe]-filen.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurera [!DNL Insight.cfg] för tecken med enkel eller dubbel byte.

   Data workbench har för närvarande stöd för både engelska och förenklad kinesiska. Du kan välja teckensnitt som har stöd för båda dessa språk:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Starta om [!DNL Insight.exe].

