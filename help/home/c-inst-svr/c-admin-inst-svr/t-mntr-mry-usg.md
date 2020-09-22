---
description: Information om bedömning och övervakning av adressutrymmesbelastningen.
solution: Analytics
title: Övervaka minnesanvändning
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 1%

---


# Övervaka minnesanvändning{#monitoring-memory-usage}

Information om bedömning och övervakning av adressutrymmesbelastningen.

**Övervaka adressutrymmesinläsningen**

**Rekommenderad frekvens:** Dagligen

Inläsningen av adressutrymme är ett mått på den del av det maximala adressutrymmet som används av korrekt konfigurerade [!DNL Insight Server] användare. Även om konfigurationsparametrarna ändras för att minska minnesanvändningen minskar den vanligtvis inte förrän tjänsten startas om [!DNL Insight Server] .

En säkerhetsmarginal har byggts in i adressutrymmets maximala inläsning för att kompensera för oväntade ökningar i adressutrymmesanvändningen. Du ska aldrig avsiktligt klippa dig in i den här säkerhetsmarginalen. Det finns för krissituationer och inte för stöd av funktioner som lagts till i Adobe.

>[!NOTE]
>
>Om du vill göra mer adressutrymme tillgängligt och undvika minnesöverbelastningsfel kontrollerar du att växeln /3 GB är aktiverad i operativsystemet och att stacken för låg fragmentering används.

Fel som loggas till [!DNL Insight Server] händelseloggen kan ge en ledtråd om att problem utvecklas med adressutrymmesinläsningen:

* Felen &quot;Begärt X-byteblock är för stort&quot; anger att något kan ha en för stor inverkan på adressutrymmesbelastningen, prestanda och nätverksbandbredd. Sådana stora block kan bidra mycket till adressutrymmesanvändningen, både genom att använda mycket minne och genom att kräva stora sammanhängande block av adressutrymme.

   Du kan åtgärda det här problemet genom att minska kardinaliteten för dina största dimensioner, vilket ökar belastningen på adressutrymmet. Om du inte kan minska dimensionernas kardinalitet bör du försöka hålla adressutrymmet tillräckligt litet så att du kan hantera en oväntad ökning.
* Felen &quot;Minnesbudgeten överskreds&quot; indikerar att du kan behöva öka gränsen för frågeminnet. Minne som används av frågor står i proportion till dimensionskardinaliteten och, i vissa fall, längden på elementnamnen. Om du ökar gränsen för frågeminne ökar du den totala belastningen på adressutrymmet och minskar storleken.

>[!NOTE]
>
>Som standard tillåts stora sidor och minnesmappad sökning är inaktiverad. I DWB 6.7 och senare kan detta ändras i datauppsättningskonfigurationen. Servern måste startas om för alla ändringar.

**Utvärdera belastningen på adressutrymmet**

Adobe rekommenderar att du bearbetar datauppsättningen på nytt, utför vanliga frågor utan att starta om [!DNL Insight Server]och sedan visar den uppmätta belastningen på adressutrymmet genom att följa dessa steg för att utvärdera belastningen på adressutrymmet korrekt.

Om en [!DNL Insight Server] inte har bearbetats på nytt och efterfrågats avsevärt sedan den startades om senast bör du inte dra några slutsatser från belastningen på adressutrymmet.

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för det [!DNL Insight Server] du vill konfigurera och klicka sedan på **[!UICONTROL Detailed Status]**.
1. Klicka på i gränssnittet Detaljerad status **[!UICONTROL Memory Status]** för att visa innehållet. I parametern Load för adressutrymme kan du se belastningen på adressutrymmet i procent och en parentetisk beskrivning som anger status.

   I följande tabell visas intervall och status för adressutrymmesinläsning. En rekommenderad åtgärd visas för varje intervall.

   | Adressutrymme inläst (%) | Status | Rekommenderad åtgärd |
   |---|---|---|
   | 0-15 | mager och medelgod | Ingen. |
   | 15-33 | ljus | Ingen. |
   | 33-66 | måttlig | Ingen. |
   | 66-100 | tung | För att undvika minnesöverbelastningsfel bör du inte lägga till någon större extrafunktion eller försöka att bearbeta mer data. |
   | 100-125 | tillförlitligheten har komprometterats | Justera datauppsättningskonfigurationen för att minska belastningen på adressutrymmet. |
   | 125 eller högre | förestående misslyckande | Justera datauppsättningskonfigurationen för att minska belastningen på adressutrymmet. Du kanske inte ser att felet är överhängande innan det inträffar. |

   Om belastningen på adressutrymmet överstiger 100 % bör du ändra konfigurationen så snart som möjligt för att minska användningen av adressutrymmet.

