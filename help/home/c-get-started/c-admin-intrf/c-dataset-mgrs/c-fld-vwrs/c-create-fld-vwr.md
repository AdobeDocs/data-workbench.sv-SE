---
description: Du kan öppna ett fältvisningsprogram som en bildtext från en beroendekarta eller som en fristående visualisering på Admin-menyn.
title: Skapa ett fältvisningsprogram
uuid: df48e728-96f9-4432-82c8-f8047840ffb9
exl-id: a2563dbb-1d1f-4ed8-b73b-6ac7a2687405
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# Skapa ett fältvisningsprogram{#create-a-field-viewer}

Du kan öppna ett fältvisningsprogram som en bildtext från en beroendekarta eller som en fristående visualisering på Admin-menyn.

## Skapa ett fältvisningsprogram från en beroendekarta {#section-040cb83c902b49c48b841d35abc127e5}

När du öppnar ett fältvisningsprogram från en beroendekarta (som visas i [Öppna fältvisningsprogram](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-opn-field-vwrs.md#concept-0f0738ac50804a33818487222c337c27)) fylls visningsprogrammet i automatiskt baserat på loggkällan, omvandlingen eller dimensionen som du högerklickar på. För en loggkälla eller en omformning är fälten i visningsprogrammet indata eller utdata från loggkällan eller omformningen. För en dimension är fälten indata för dimensionen. Du kan lägga till och ta bort fält efter behov.

## Skapa en fältvisare som en fristående visualisering {#section-11d10e46631d4fdca45d7534336e1e80}

När du öppnar ett fältvisningsprogram som en fristående visualisering kan du skapa en [!DNL Log Processing Field Viewer] eller en [!DNL Transformation Field Viewer]. Visningsprogrammet är tomt och du måste lägga till önskade fält i visningsprogrammet. För en [!DNL Log Processing Field Viewer] kan du lägga till fält från [!DNL Log Processing.cfg]-filen eller valfri [!DNL Log Processing dataset include]-fil. För en [!DNL Transformation Field Viewer] kan du lägga till fält från [!DNL Transformation.cfg]-filen eller valfri [!DNL Transformation dataset include]-fil.

Mer information om konfiguration och inkluderingsfiler finns i *Konfigurationshandboken för datauppsättningar*.

## Lägg till och ta bort ett fält {#section-9c0d4f5735a044a8b21dc7a99c63a59a}

**Lägga till ett fält i ett fältvisningsprogram**

* Högerklicka i fältvisningsprogrammet och klicka på **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

   -or-

* Högerklicka i en befintlig kolumn i fältvisningsprogrammet och klicka på **[!UICONTROL Fields]** > *&lt;**[!UICONTROL field name]**>* > *&lt;**[!UICONTROL instance]**>*.

Fältnamnet refererar till fältets namn, och instansen refererar till var i datauppsättningskonfigurationen fältet används, till exempel en datauppsättningsbearbetningsfas eller en transformering. Vissa fält används på flera ställen i datauppsättningskonfigurationen (ett fält kan till exempel ändras av flera omformningar), så du måste välja vilken instans av fältet som ska läggas till i visningsprogrammet för fältet.

I listan med tillgängliga fält visas ett X till vänster om alla fält som redan visas i visningsprogrammet.

**Så här tar du bort ett fält från ett fältvisningsprogram**

* Högerklicka i kolumnen för det fält som du vill ta bort och klicka på **[!UICONTROL Remove Field]**.
