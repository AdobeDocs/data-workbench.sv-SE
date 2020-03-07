---
description: Innan du konfigurerar experimentet bör du skapa det alternativa innehåll som du vill använda i experimentet.
solution: Insight,Analytics
title: Skapa testinnehåll
topic: Data workbench
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skapa testinnehåll{#creating-the-test-content}

Innan du konfigurerar experimentet bör du skapa det alternativa innehåll som du vill använda i experimentet.

Kontrollgruppen skickas till den ursprungliga URI:n medan testgruppen skickas till den nya, alternativa URI:n.

Undvik förvirring genom att inte återanvända filnamn för testgrupper. Om du till exempel kör ett experiment med en testgruppsfil med namnet [!DNL test2.asp], ska du inte använda [!DNL test2.asp] som namn för testfilen i nästa experiment.

Om vi antar att flytten av den grafiska länken &quot;Begär en demo&quot; på din hemsida påverkar besökskonverteringen, skapar vi den alternativa hemsidan med den grafiska länken &quot;Begär en demo&quot; på den nya positionen. I följande avsnitt beskrivs hur du sedan anger att kontrollgruppens URI [!DNL index.asp] ska ersättas med testgruppens URI [!DNL index2.asp] för en viss procentandel av besökarna.