---
description: När du konfigurerar datauppsättningen kan du definiera variabler, så kallade parametrar, som representerar meningsfulla värden.
solution: Analytics
title: Definiera parametrar i datauppsättningen inkluderar filer
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definiera parametrar i datauppsättningen inkluderar filer{#defining-parameters-in-dataset-include-files}

När du konfigurerar datauppsättningen kan du definiera variabler, så kallade parametrar, som representerar meningsfulla värden.

Om du vill tilldela ett värde till en parameter (det vill säga definiera parametern) lägger du till parameterns namn och värde i parametervektorn i en loggbearbetning eller [!DNL Transformation Dataset Include] fil. När du har definierat parametrar kan du referera till dem i datauppsättningsprofilens konfigurationsfiler. Att definiera och referera till sådana parametrar kallas parameterersättning. Genom att använda parameterersättning när du konfigurerar datauppsättningen kan du skapa en central plats för parameterdefinitionerna. När du behöver uppdatera en parameter som refereras flera gånger eller i flera filer, måste du bara göra ändringen en gång.

>[!NOTE]
>
>I den här handboken har termen parameter använts för att referera till namnet på en inställning i en konfigurationsfil (t.ex. Loggpostvillkor, Återbearbetning eller Omformningar). I det här avsnittet refererar parametern emellertid specifikt till en medlem i parametervektorn i en datauppsättning som innehåller fil och inte till namnet på en inställning i en konfigurationsfil.

Du bör tänka på följande när du definierar en parameter:

* En parameter måste definieras exakt en gång. Därför kan du inte definiera samma variabel i flera datauppsättningar som innehåller filer.
* Alla parametrar som du definierar är lokala för antingen loggbearbetningen eller transformeringsfaserna, men globala för flera datauppsättningskonfigurationsfiler för den fasen. Om du till exempel definierar en parameter i en [!DNL Transformation Dataset Include] fil, definieras parametern för hela omformningsfasen och du kan referera till den i [!DNL Transformation.cfg] filen och alla andra [!DNL Transformation Dataset Include] filer för de ärvda profilerna. Parametern skulle inte definieras för loggbearbetning. Därför genererar alla referenser till parametern i [!DNL Log Processing.cfg] filen eller en [!DNL Log Processing Dataset Include] fil ett bearbetningsfel.

**Definiera en parameter**

Du kan definiera parametrar för strängar, siffror och vektorer i [!DNL Log Processing] - och [!DNL Transformation Include] -filer.

1. Högerklicka i datafönstret för filen [!DNL Log Processing] eller [!DNL Transformation Dataset Include] filen **[!UICONTROL Parameters]** och klicka sedan **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. Välj **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]** eller **[!UICONTROL Vector Parameter]** och fyll i parametrarna Namn och Värde enligt beskrivningen i följande avsnitt.

1. Om du vill spara datauppsättningsfilen där du har definierat parametern högerklickar du **[!UICONTROL (modified)]** längst upp i fönstret och klickar på **[!UICONTROL Save]**.

1. Om du vill göra de lokalt gjorda ändringarna gällande [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör.

>[!NOTE]
>
>Spara inte den ändrade konfigurationsfilen i någon av de interna profiler som tillhandahålls av Adobe, eftersom dina ändringar skrivs över när du installerar uppdateringar för dessa profiler.

**Referera till en parameter**

* När du refererar till en definierad parameter i en annan datauppsättningskonfigurationsfil måste du skriva dess namn som [!DNL $(parameter name)].

I följande avsnitt beskrivs de parametertyper som du kan definiera.

* [Sträng- och numeriska parametrar](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [Vektorparametrar](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
