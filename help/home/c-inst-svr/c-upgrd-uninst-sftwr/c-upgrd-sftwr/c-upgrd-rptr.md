---
description: Instruktioner för att uppgradera Repeater med Insight eller för att uppgradera genom att kopiera filer.
title: Uppgraderar upprepning
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Uppgraderar upprepning{#upgrading-repeater}

Instruktioner för att uppgradera Repeater med Insight eller för att uppgradera genom att kopiera filer.

Du kan använda någon av följande metoder för att uppgradera [!DNL Repeater] från Platform 4.x eller senare:

* Om du skapade en anslutning mellan [!DNL Insight] och [!DNL Repeater] enligt beskrivningen i [Skapa en anslutning mellan Insight och Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118) kan du använda [!DNL Insight] för att uppgradera [!DNL Repeater]. Se [Uppgradera upprepning med Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -or-

* Om du inte kunde eller inte kunde skapa en anslutning mellan [!DNL Insight] och [!DNL Repeater] måste du kopiera uppgraderingsfilerna direkt till [!DNL Repeater]-datorn. Se [Uppgradera upprepning genom att kopiera filer](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Uppgraderar upprepning med Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. På [!DNL Insight]-datorn kopierar du mappen [!DNL bin] från [!DNL Insight Server]-uppgraderingspaketet till [!DNL Temp]-mappen i den katalog där [!DNL Insight] är installerat.
1. Starta [!DNL Insight].
1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Repeater] som du vill uppgradera och klicka på **[!UICONTROL Server Files]**.
1. I [!DNL Server Files Manager] gör du följande för att överföra uppgraderingsfilerna till servern:

   1. Leta reda på mappen [!DNL bin].
   1. Högerklicka på bockmarkeringen för mappen [!DNL bin] i katalogen Temp och välj **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Du kommer att se ett meddelande om att det här steget skriver över filer med samma namn som finns på servern. Klicka på **[!UICONTROL Yes]** för att fortsätta.

>[!NOTE]
>
>Om du behöver ladda upp ytterligare filer för att slutföra uppgraderingen av [!DNL Repeater], kommer Adobe att ge instruktioner om att göra det.

När du har överfört uppgraderingsfilerna till [!DNL Repeater]-datorn startar [!DNL Repeater] automatiskt om och läser in den nya versionen.

## Uppgradera upprepning genom att kopiera filer {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Öppna uppgraderingsfilen från Adobe. Den här filen är troligen en [!DNL .zip]-fil för uppgradering av [!DNL Insight Server].
1. Gå till katalogen där du installerade [!DNL Repeater] (till exempel [!DNL D:\Adobe\Repeater]).
1. Kopiera mappen [!DNL bin] i filen [!DNL .zip] och klistra in den i installationskatalogen för [!DNL Repeater] för att skriva över den befintliga mappen [!DNL bin].

>[!NOTE]
>
>Om du behöver ladda upp ytterligare filer för att slutföra uppgraderingen av [!DNL Insight Server], kommer Adobe att ge instruktioner om att göra det.

När du har kopierat uppgraderingsfilerna till [!DNL Repeater]-datorn startar [!DNL Repeater] automatiskt om och läser in den nya versionen.
