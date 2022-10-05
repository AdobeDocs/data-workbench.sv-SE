---
description: Med sidofältet får du tillgång till funktioner som används ofta och bevarar visualiseringar när du växlar mellan arbetsytor.
title: Konfigurera sidlisten
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 0%

---

# Konfigurera sidlisten{#configure-the-sidebar}

{{eol}}

Med sidofältet får du tillgång till funktioner som används ofta och bevarar visualiseringar när du växlar mellan arbetsytor.

Administratörer kan anpassa ett sidofält så att det passar olika användargrupper och sedan distribuera sidofältet med en profil.

Sidlisten är idealisk för att du ska kunna hålla reda på filter och lokala åsidosättningar. Om du inte vill använda sidlisten kan du dölja den.

## Lägg till visualiseringar i sidofältet {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Starta Datan Workbench.
1. Klicka på **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. Till exempel: [!DNL Selections Panel], [!DNL Filters Panel], eller [!DNL Table].

   Följande sidopaneler är tillgängliga i standardinstallationen av Data Workbench. Fler objekt kan vara tillgängliga i din specifika profil:

   * **Panelen Markeringar:** Gör att du kan förstå vilka markeringar som är aktiva på den aktuella arbetsytan. The [!DNL Selections Panel] uppdateras varje gång du gör ett nytt val. Du kan rensa markeringar genom att klicka **[!UICONTROL x]**. Se [Göra markeringar i visualiseringar](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) om du vill ha information om hur du väljer data.
   * **Panelen Filter:** Gör det enkelt att läsa in och använda sparade filter. Du kan läsa in flera filter och aktivera eller inaktivera vart och ett av dem separat genom att klicka i kryssrutan bredvid det. Se [Filterredigerare](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Lokal åsidosättningspanel:** Den här panelen visar vilka mått, dimensioner och filter som finns i profilen som har ändrats i din personliga kopia av profilen. Detta hjälper dig att uppmärksamma dig på eventuella skillnader mellan hur data visas i din klient och i andra användares. När du sparar ändringar i ett mått, en dimension eller ett filter på servern tas åsidosättningen bort från [!DNL Local Overrides panel]. Om du klickar på en åsidosättning och sedan klickar på **[!UICONTROL Revert to Server]**, tas den lokala åsidosättningen bort och objektet återställs till den delade versionen.
   * **Måttförklaring:** Lägger till en måttförklaring. [!DNL Metric legends] gör att du kan se baslinjevärden relaterade till din profil och statistik relaterad till datauppsättningen (eller till det aktuella urvalet, om ett sådant har gjorts). Se [Metriska förklaringar](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **Färgförklaring:** Lägger till en färgförklaring. Du kan färgkoda visualiseringar efter mätvärden, som Konvertering och Kvarhållning, och använda dem i nästan varje [!DNL Workspace]. Genom att länka affärsstatistik till färg blir det enkelt att upptäcka avvikelser, undantag och trender. Se [Färgförklaringar](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).
   * **Textanteckning:** Lägger till en anteckningspanel. [!DNL Text annotations] är fönster där du kan ange godtycklig text för att lägga till beskrivande information eller kommentarer i en [!DNL Workspace]. Se [Arbeta med textanteckningar](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **Tabell:** Lägger till en tabell. En tabell kan visa en eller flera mätvärden över en eller flera datamängder. Se [Tabeller](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Öppna:** Öppnar en sparad fil.

## Öppna en sidofältspanel {#section-cbc8e57491854274a577d47a48c306b8}

Du kan öppna en sidofältsvisualiseringsfil från en sparad plats eller från Urklipp.

1. Klicka på **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Klicka **[!UICONTROL File]** för att hitta [!DNL .vw] filen för panelen som du vill lägga till, eller klicka på **[!UICONTROL Last Closed Window]**, som hämtar visualiseringen från Urklipp.

   Dessutom kan du klicka **[!UICONTROL From Clipboard]** om du vill klistra in en visualisering som har kopierats till Urklipp. Se [Kopiera en sidofältspanel](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1).

## Kopiera en sidofältspanel {#section-720ae057632a4b8dbb94412e06a370b1}

1. Högerklicka på panelens övre kant och klicka sedan på **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Klistra in panelen genom att klicka **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Spara en sidofältspanel {#section-fb19936b12704fb0a4c592abb579db1d}

Högerklicka i namnlisten på en sidofältspanel och klicka **[!UICONTROL Save]**.

På samma sätt kan du öppna en sparad sidofältsvisualisering. Datan Workbench sparar visualiseringen som en [!DNL .vw] på den plats du anger.

## Återgå till standardsidpanelen {#section-4d14b8771ad747bba799876267f24831}

Klicka på **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

När du stänger Data Workbench sparas den aktuella sidofältskonfigurationen i [!DNL sidebar.vw] i användarprofilen. När du öppnar Data Workbench läses systemet in [!DNL sidebar.vw] från användarprofilen i stället för en överordnad profil.

Du kan återgå till ett standardsidofält eller ett sparat sidofält, som tar bort sidofältet från användarprofilen och läser in sidofältet igen från den överordnade profilen. Administratörer kan ersätta standardsidofältet (överordnat) med ett lokalt sidofält genom att överföra det från [!DNL Profile Manager].

## Anpassa filen med panelen Mer status {#section-8d502f3b59cc4331966edec05e896ce1}

Systemadministratörer kan skapa formler i [!DNL More Status Panel.vw]. Detta placerar sammanhangsbaserade ord runt mått och dimensionsvärden och visar resultaten i [!DNL More Status panel] i sidlisten.

Visa [!DNL More Status panel] Klicka på pilarna som visas i följande exempel i sidlisten.

![](assets/more_status_panel_arrows.png)

I följande procedur visas ett enkelt exempel på hur du skapar en anpassad status som anger hur många dagar som finns i en datauppsättning:

1. I [!DNL Profile Manager], klicka **[!UICONTROL Sidebar\]**.

1. I [!DNL Base_5_3*] gör du en lokal kopia av [!DNL More Status Panel.vw] -fil.

   Om du vill göra det högerklickar du på filens bockmarkering och klickar på **[!UICONTROL Make Local]**.

1. Öppna [!DNL More Status Panel.vw] i [!DNL .vw] [!DNL Editor] eller i Anteckningar.

   ![](assets/more_status_panel_file.png)

1. Slutför [!DNL Context] och [!DNL Items] fälten i [!DNL Editor]. Se [Syntax för frågespråk](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) för riktlinjer om syntax.

1. Spara filen.

   Värdena i föregående exempel resulterar i en statusformel som visas enligt följande:

   ![](assets/more_status_panel.png)
