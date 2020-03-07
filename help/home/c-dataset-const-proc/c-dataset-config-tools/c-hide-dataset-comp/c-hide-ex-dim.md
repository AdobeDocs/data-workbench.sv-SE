---
description: Du kan antingen använda parametern Dold eller parametern Show för att dölja utökade dimensioner så att de inte visas på dimensionsmenyn i data workbench.
solution: Analytics
title: Dölja utökade dimensioner
topic: Data workbench
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Dölja utökade dimensioner{#hiding-extended-dimensions}

Du kan antingen använda parametern Dold eller parametern Show för att dölja utökade dimensioner så att de inte visas på dimensionsmenyn i data workbench.

När du anger rätt inställning för någon av parametrarna visas inte dimensionsnamnet på menyn i data workbench, men det finns fortfarande i profilen och kan användas. Alla användare av Data Workbench kan tillfälligt visa dolda dimensioner genom att ställa in parametern Visa alla i [!DNL Insight.cfg] filen på true.

Mer information om parametern Visa alla finns i bilagan om konfigurationsparametrar för data workbench i *användarhandboken* för Data Workbench.

I följande avsnitt beskrivs hur du använder parametrarna Dold och Visa för att dölja de utökade dimensionerna.

* [Dölja utökade dimensioner med parametern Dold](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Dölja utökade dimensioner med parametern Show](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Dölja utökade dimensioner med parametern Dold {#section-7167a6f6241a4bc78f2f322e048d65cf}

Parametern Dold är en valfri parameter som du kan använda när du definierar utökade dimensioner i [!DNL Transformation Dataset Configuration] filer.

1. Öppna [!DNL Transformation Dataset Configuration] filer där den utökade dimension som du vill dölja är definierad. Se [Redigera befintlig datauppsättning Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Leta reda på parametern Dold för den önskade dimensionen i konfigurationsfönstret och skriv *true*.
1. Spara filen lokalt och spara den sedan i lämplig profil på servern. Se [Redigera befintlig datauppsättning Inkludera filer](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

Datauppsättningen omformas, varefter den utökade dimensionen inte visas på dimensionsmenyn i data workbench. Mer information om parametern Dold finns i [Utökade dimensioner](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Om du ändrar inställningen för parametern Dold måste du omforma datauppsättningen för att ändringen ska börja gälla.

## Dölja utökade dimensioner med parametern Show {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

Parametern Visa är inte en av de parametrar som är tillgängliga för att definiera utökade dimensioner i [!DNL Transformation Dataset Configuration] filer. I stället definieras parametern i [!DNL .dim] filerna för alla härledda dimensioner som du skapar. Om du vill använda parametern Visa för att dölja en utökad dimension måste du därför först skapa en härledd dimension som baseras på den utökade dimensionen enligt följande procedur:

1. Använd en textredigerare som Anteckningar för att skapa en tom fil med namnet &lt;*dimensionsnamn*>.dim Filnamnet ska matcha namnet på dimensionen som du vill dölja. Om du till exempel vill dölja dimensionen Nästa sida skapar du en [!DNL Next Page.dim] fil.

1. Lägg till följande text i filen:

   * enhet = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. Spara filen i profilens Dimensions-katalog. Du kan spara filen i en underkatalog om du vill.

När du använder parametern Show för att dölja en utökad dimension behöver du inte omforma datauppsättningen för att ändringen ska börja gälla. Du kan välja att dölja eller visa dimensionen i din lokala version av profilen (d.v.s. du kan spara [!DNL .dim] filen i din användarmapp) eller så kan du spara [!DNL .dim] filen på servern och använda den av andra användare.

Du kan också använda parametern Visa för att dölja mått och filter. Mer information finns i kapitlet Konfigurera gränssnitt och analysfunktioner i *användarhandboken* för Data Workbench.
