---
description: Om du vill ange vilka profiler som ska vara tillgängliga i rapportportalen måste du konfigurera filen profiles.xml.
solution: Analytics
title: Redigera filen Profiles.xml
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Redigera filen Profiles.xml{#edit-the-profiles-xml-file}

Om du vill ange vilka profiler som ska vara tillgängliga i rapportportalen måste du konfigurera filen profiles.xml.

Filen finns i den mapp som du har angett för utdata [!DNL profiles.xml] . Som standard finns den i mappen \*PortalName*\PortalFiles\Output folder.

**Lägga till profilnamn i filen profiles.xml**

1. Öppna filen i en textredigerare, t.ex. Anteckningar, på den dator där IIS körs. [!DNL profiles.xml]
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
