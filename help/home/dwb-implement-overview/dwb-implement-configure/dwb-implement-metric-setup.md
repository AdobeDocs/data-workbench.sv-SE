---
description: I det här avsnittet beskrivs hur du skapar mätvärden i Data Workbench.
title: Mätinställningar
uuid: 57c1410b-c09c-4a59-b3a1-575323e1b8e3
exl-id: a60c08d3-f708-43be-a14f-8b7f129f3ee5
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Mätinställningar{#metrics-setup}

I det här avsnittet beskrivs hur du skapar mätvärden i Data Workbench.

## Förstå mått {#section-f0412e851fcb4ac9886dca4003d42cec}

Mätvärden är kvantitativ information om kundaktivitet, t.ex. vyer, beställningar, antal anrop och intäkter. Mätvärden är grunden för rapporter och hjälper er att visa och förstå datarelationer.

Med Dimensionen Metrisk kan du gruppera måttantal efter en viss nivå. Du kan också gruppera mätvärden på en viss nivå.

## Skapa nya mått {#section-60a413899d1b4707965e06fb5ef7fc4e}

Följ stegen nedan för att skapa ett nytt mått:

1. Klicka på **Verktyg** > **Måtredigeraren**.

1. Ange det nya måttnamnet och formeln i måttredigeraren. ![](assets/dwb_impl_metrics1.png)

1. Spara den i mappen Metrics. ![](assets/dwb_impl_metrics2.png)

## Skapa och redigera härledda mått {#section-ebdcd3ec652f485e90e001d694eab6d0}

Använd en metadataredigerare för att definiera ett nytt mått efter namn, formel och format, som sparas i mappen [!DNL User\profile_name\Metrics] för senare bruk.

1. Öppna en ny måttredigerare med menyalternativet **Admin > Profil** eller högerklicka på kolumnen Användare för den mapp där du vill skapa måttet och klicka på **Skapa > Nytt mått**. En metrisk redigerare visas.

1. I parametern *Namn* anger du ett namn för det nya måttet.

   >[!NOTE]
   >
   >Observera att mellanslag ( ) tillåts men understreck (_) inte. Du kan inte heller använda följande symboler: + - * /

   ![](assets/dwb_impl_metrics3.png)

1. I parametern *Formula* skriver du ett uttryck för det nya måttet.

   >[!NOTE]
   Filter måste definieras inom hakparenteser [ ] i uttrycket. Ytterligare syntaxregler för uttryck i mätvärden finns i [Syntax for Metric Expression.](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

   Den här tabellen innehåller exempeluttryck för utökade mått. ![](assets/dwb_impl_metrics4.png)

   >[!NOTE]
   När ett lämpligt uttryck anges visas värdet för det nya måttet på förhandsvisningsraden. Om det finns ett fel i uttrycket visar förhandsvisningsraden ett felmeddelande.

1. Högerklicka och välj **Spara**. När du sparar måttet skapas en fil som representerar det nya måttet på datorn i DWB-mappen *\User\profile name\Metrics*.

## Redigera befintliga härledda mått {#section-4b5b7baf885b45cc8b358d1bd774e925}

1. Högerklicka på bockmarkeringen för den metriska fil som du vill redigera i kolumnen Profilhanteraren eller Metrics Manager och klicka på **Gör lokal**.
1. Högerklicka på bockmarkeringen för måttfilen i kolumnen Användare och klicka på **Öppna** i workbench.

   >[!NOTE]
   Du kan också öppna en metadataredigerare genom att högerklicka på ett mätrelaterat område i en visualisering för att visa mätmenyn.

1. I **Metrisk redigerare** redigerar och sparar du måttdefinitionen med Steg 2-4 i *Skapa nya härledda mått*.

   Om du vill att alla användare av profilen ska använda det mått som du redigerade måste du publicera det i arbetsprofilen med hjälp av Profilhanteraren.

Mer hjälp finns i dokumentationen:

[Syntax för måttuttryck](https://experienceleague.adobe.com/docs/data-workbench/using/client/qry-lang-syntx/c-syntx-mtrc-exp.html)

[Skapa och redigera härledda mått](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/profile-mgr/c-drvd-mtrcs.html)
