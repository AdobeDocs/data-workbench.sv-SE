---
description: När du konfigurerar datauppsättningen kan du definiera variabler, så kallade parametrar, som representerar meningsfulla värden.
title: Definiera parametrar i datauppsättningen inkluderar filer
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---

# Definiera parametrar i datauppsättningen inkluderar filer{#defining-parameters-in-dataset-include-files}

{{eol}}

När du konfigurerar datauppsättningen kan du definiera variabler, så kallade parametrar, som representerar meningsfulla värden.

Om du vill tilldela ett värde till en parameter (det vill säga definiera parametern) lägger du till parameterns namn och värde i parametervektorn i en loggbearbetning eller [!DNL Transformation Dataset Include] -fil. När du har definierat parametrar kan du referera till dem i datauppsättningsprofilens konfigurationsfiler. Att definiera och referera till sådana parametrar kallas parameterersättning. Genom att använda parameterersättning när du konfigurerar datauppsättningen kan du skapa en central plats för parameterdefinitionerna. När du behöver uppdatera en parameter som refereras flera gånger eller i flera filer, måste du bara göra ändringen en gång.

>[!NOTE]
>
>I den här handboken har termen parameter använts för att referera till namnet på en inställning i en konfigurationsfil (t.ex. Loggpostvillkor, Återbearbetning eller Omformningar). I det här avsnittet refererar parametern emellertid specifikt till en medlem i parametervektorn i en datauppsättning som innehåller fil och inte till namnet på en inställning i en konfigurationsfil.

Du bör tänka på följande när du definierar en parameter:

* En parameter måste definieras exakt en gång. Därför kan du inte definiera samma variabel i flera datauppsättningar som innehåller filer.
* Alla parametrar som du definierar är lokala för antingen loggbearbetningen eller transformeringsfaserna, men globala för flera datauppsättningskonfigurationsfiler för den fasen. Om du till exempel definierar en parameter i en [!DNL Transformation Dataset Include] -filen, definieras parametern för hela omformningsfasen och du kan referera till den i [!DNL Transformation.cfg] och alla andra [!DNL Transformation Dataset Include] filer för de ärvda profilerna. Parametern skulle inte definieras för loggbearbetning. därför alla referenser till parametern i [!DNL Log Processing.cfg] eller en [!DNL Log Processing Dataset Include] filen skulle generera ett bearbetningsfel.

**Definiera en parameter**

Du kan definiera strängparametrar, numeriska parametrar och vektorparametrar i [!DNL Log Processing] och [!DNL Transformation Include] filer.

1. I data workbench-fönstret för [!DNL Log Processing] eller [!DNL Transformation Dataset Include] fil, högerklicka **[!UICONTROL Parameters]** och sedan klicka **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Välj **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]**, eller **[!UICONTROL Vector Parameter]** och fyll i parametrarna Namn och Värde så som beskrivs i följande avsnitt.

1. Om du vill spara datauppsättningsfilen där du har definierat parametern högerklickar du **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

1. Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör.

>[!NOTE]
>
>Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

**Referera till en parameter**

* När du refererar till en definierad parameter i en annan datauppsättningskonfigurationsfil måste du skriva dess namn som [!DNL $(parameter name)].

I följande avsnitt beskrivs de parametertyper som du kan definiera.

* [Sträng- och numeriska parametrar](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Vektorparametrar](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
