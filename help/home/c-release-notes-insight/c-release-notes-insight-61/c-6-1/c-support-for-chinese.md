---
description: Klientprogrammet data workbench har nu stöd för förenklad kinesiska.
solution: Analytics
title: Förenklad kinesisk lokalisering
topic: Data workbench
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Förenklad kinesisk lokalisering{#simplified-chinese-localization}

Klientprogrammet data workbench har nu stöd för förenklad kinesiska.

**Så här installerar du förenklad kinesiska**:

Innan du konfigurerar [!DNL Insight.exe] och stöder filer måste du avsluta klientprogrammet.

1. Skapa ett kortkommando som skickas i kommandoradsinställningen till [!DNL insight.exe] filen.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurera [!DNL Insight.cfg] för tecken med en eller två byte.

   Data workbench har för närvarande stöd för både engelska och förenklad kinesiska. Du kan välja teckensnitt som har stöd för båda dessa språk:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Starta om [!DNL Insight.exe].

