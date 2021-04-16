---
description: Om du vill ange vilka profiler som ska vara tillgängliga i rapportportalen måste du konfigurera filen profiles.xml.
title: Redigera filen Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 0%

---

# Redigera filen Profiles.xml{#edit-the-profiles-xml-file}

Om du vill ange vilka profiler som ska vara tillgängliga i rapportportalen måste du konfigurera filen profiles.xml.

Filen [!DNL profiles.xml] finns i den mapp som du har angett för utdata. Som standard finns den i mappen \*PortalName*\PortalFiles\Output folder.

**Lägga till profilnamn i filen profiles.xml**

1. Öppna [!DNL profiles.xml]-filen i en textredigerare, t.ex. Anteckningar, på den dator där IIS körs.
1. Lägg till ett profilelement och en tagg för varje [!DNL Profile] i portalen, som i följande exempel:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. Spara och stäng filen.
