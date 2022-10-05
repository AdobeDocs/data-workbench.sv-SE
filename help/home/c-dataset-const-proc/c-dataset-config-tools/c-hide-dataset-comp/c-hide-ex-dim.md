---
description: Du kan antingen använda parametern Dold eller parametern Show för att dölja utökade dimensioner så att de inte visas på dimensionsmenyn i data workbench.
title: Dölja utökade Dimensioner
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 0%

---

# Dölja utökade Dimensioner{#hiding-extended-dimensions}

{{eol}}

Du kan antingen använda parametern Dold eller parametern Show för att dölja utökade dimensioner så att de inte visas på dimensionsmenyn i data workbench.

När du anger rätt inställning för någon av parametrarna visas inte dimensionsnamnet på menyn i data workbench, men det finns fortfarande i profilen och kan användas. Alla användare av Data Workbench kan tillfälligt visa dolda dimensioner genom att ställa in parametern Visa alla i [!DNL Insight.cfg] filen är true.

Mer information om parametern Ta fram alla finns i bilagan om konfigurationsparametrarna för data workbench i *Användarhandbok för Data Workbench*.

I följande avsnitt beskrivs hur du använder parametrarna Dold och Visa för att dölja de utökade dimensionerna.

* [Dölja utökade Dimensioner med parametern Dold](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Dölja utökade Dimensioner med parametern Visa](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Dölja utökade Dimensioner med parametern Dold {#section-7167a6f6241a4bc78f2f322e048d65cf}

Parametern Dold är en valfri parameter som du kan använda när du definierar utökade dimensioner i [!DNL Transformation Dataset Configuration] filer.

1. Öppna [!DNL Transformation Dataset Configuration] filer där den utökade dimension som du vill dölja är definierad. Se [Redigera befintlig datauppsättning Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Leta reda på parametern Dold för den önskade dimensionen i konfigurationsfönstret och skriv *true*.
1. Spara filen lokalt och spara den sedan i lämplig profil på servern. Se [Redigera befintlig datauppsättning Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Datauppsättningen omformas, varefter den utökade dimensionen inte visas på dimensionsmenyn i data workbench. Mer information om parametern Dold finns i [Utökade Dimensioner](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Om du ändrar inställningen för parametern Dold måste du omforma datauppsättningen för att ändringen ska börja gälla.

## Dölja utökade Dimensioner med parametern Visa {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Parametern Show är inte en av parametrarna som används för att definiera utökade dimensioner i [!DNL Transformation Dataset Configuration] filer. I stället definieras parametern i [!DNL .dim] filer för alla härledda dimensioner som du skapar. Om du vill använda parametern Visa för att dölja en utökad dimension måste du därför först skapa en härledd dimension som baseras på den utökade dimensionen enligt följande procedur:

1. Använd en textredigerare som Anteckningar för att skapa en tom fil med namnet &lt;*dimensionsnamn*>.dim Filnamnet måste matcha namnet på dimensionen som du vill dölja. Om du till exempel vill dölja dimensionen för nästa sida skapar du en [!DNL Next Page.dim] -fil.

1. Lägg till följande text i filen:

   * enhet = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. Spara filen i profilens katalog för Dimensioner. Du kan spara filen i en underkatalog om du vill.

När du använder parametern Show för att dölja en utökad dimension behöver du inte omforma datauppsättningen för att ändringen ska börja gälla. Du kan välja att dölja eller visa dimensionen i din lokala version av profilen (det vill säga, du kan spara [!DNL .dim] till din användarmapp) eller så kan du spara [!DNL .dim] till servern för att användas av andra användare av profilen.

Du kan också använda parametern Visa för att dölja mått och filter. Mer information finns i kapitlet Konfigurera gränssnitt och analysfunktioner i *Användarhandbok för Data Workbench*.
