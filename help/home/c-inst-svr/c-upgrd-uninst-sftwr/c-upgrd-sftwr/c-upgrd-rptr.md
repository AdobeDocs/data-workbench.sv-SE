---
description: Instruktioner för att uppgradera Repeater med Insight eller för att uppgradera genom att kopiera filer.
solution: Insight
title: Uppgraderar upprepning
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Uppgraderar upprepning{#upgrading-repeater}

Instruktioner för att uppgradera Repeater med Insight eller för att uppgradera genom att kopiera filer.

Du kan använda någon av följande metoder för att uppgradera [!DNL Repeater] från Platform 4.x eller senare:

* Om du har skapat en anslutning mellan [!DNL Insight] och [!DNL Repeater] enligt beskrivningen i [Skapa en anslutning mellan Insight och Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)kan du använda [!DNL Insight] för att uppgradera [!DNL Repeater]. Se [Uppgradera upprepning med Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -or-

* Om du inte kunde eller inte kunde skapa en anslutning mellan [!DNL Insight] och [!DNL Repeater]måste du kopiera uppgraderingsfilerna direkt till [!DNL Repeater] datorn. Se [Uppgradera upprepning genom att kopiera filer](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Uppgraderar upprepning med Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. På [!DNL Insight] datorn kopierar du [!DNL bin] mappen från [!DNL Insight Server] uppgraderingspaketet till [!DNL Temp] mappen i den katalog där [!DNL Insight] är installerad.
1. Börja [!DNL Insight].
1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för den [!DNL Repeater] du vill uppgradera och klicka på **[!UICONTROL Server Files]**.
1. I [!DNL Server Files Manager]exemplet gör du följande för att överföra uppgraderingsfilerna till servern:

   1. Leta reda på [!DNL bin] mappen.
   1. Högerklicka på bockmarkeringen för [!DNL bin] mappen i katalogen Temp och välj **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Du kommer att se ett meddelande om att det här steget skriver över filer med samma namn som finns på servern. Klicka **[!UICONTROL Yes]** för att fortsätta.

>[!NOTE]
>
>Om du behöver ladda upp ytterligare filer för att slutföra [!DNL Repeater] uppgraderingen får du instruktioner från Adobe om detta.

När du har överfört uppgraderingsfilerna till [!DNL Repeater] [!DNL Repeater] datorn startas de om automatiskt och den nya versionen läses in.

## Uppgradera upprepning genom att kopiera filer {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Öppna uppgraderingsfilen från Adobe. Den här filen är antagligen en [!DNL .zip] fil för uppgradering [!DNL Insight Server].
1. Gå till den katalog där du installerade [!DNL Repeater] (till exempel [!DNL D:\Adobe\Repeater]).
1. Kopiera [!DNL bin] mappen i [!DNL .zip] filen och klistra in den i din [!DNL Repeater] installationskatalog för att skriva över den befintliga [!DNL bin] mappen.

>[!NOTE]
>
>Om du behöver ladda upp ytterligare filer för att slutföra [!DNL Insight Server] uppgraderingen får du instruktioner från Adobe om detta.

När du har kopierat uppgraderingsfilerna till [!DNL Repeater] datorn startar [!DNL Repeater] automatiskt om sig själv och läser in den nya versionen.
