---
description: Om du vill ange vilka profiler som ska vara tillgängliga i rapportportalen måste du konfigurera filen profiles.xml.
title: Redigera filen Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 0%

---

# Redigera filen Profiles.xml{#edit-the-profiles-xml-file}

{{eol}}

Om du vill ange vilka profiler som ska vara tillgängliga i rapportportalen måste du konfigurera filen profiles.xml.

The [!DNL profiles.xml] filen finns i den mapp som du har angett för utdata. Som standard finns den i mappen \*PortalName*\PortalFiles\Output.

**Lägga till profilnamn i filen profiles.xml**

1. Öppna [!DNL profiles.xml] i en textredigerare som Anteckningar.
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
