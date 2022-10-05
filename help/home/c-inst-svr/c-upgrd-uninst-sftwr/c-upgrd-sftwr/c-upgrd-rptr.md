---
description: Instruktioner för att uppgradera Repeater med Insight eller för att uppgradera genom att kopiera filer.
title: Uppgraderar upprepning
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Uppgraderar upprepning{#upgrading-repeater}

{{eol}}

Instruktioner för att uppgradera Repeater med Insight eller för att uppgradera genom att kopiera filer.

Du kan uppgradera på något av följande sätt [!DNL Repeater] från Platform 4.x eller senare:

* Om du skapade en anslutning mellan [!DNL Insight] och [!DNL Repeater] enligt beskrivning i [Skapa en anslutning mellan Insight och Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)kan du använda [!DNL Insight] att uppgradera [!DNL Repeater]. Se [Uppgraderar upprepning med Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -or-

* Om du inte kunde eller inte kunde skapa en anslutning mellan [!DNL Insight] och [!DNL Repeater]måste du kopiera uppgraderingsfilerna direkt till [!DNL Repeater] dator. Se [Uppgradera upprepning genom att kopiera filer](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Uppgraderar upprepning med Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. På [!DNL Insight] dator, kopiera [!DNL bin] mapp från [!DNL Insight Server] uppgradera paketet till [!DNL Temp] mapp i katalogen där [!DNL Insight] är installerat.
1. Starta [!DNL Insight].
1. I [!DNL Insight], på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för [!DNL Repeater] du vill uppgradera och klicka på **[!UICONTROL Server Files]**.
1. I [!DNL Server Files Manager]gör du följande för att överföra uppgraderingsfilerna till servern:

   1. Leta reda på [!DNL bin] mapp.
   1. Högerklicka på bockmarkeringen för [!DNL bin] i Temp-katalogen och väljer **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Du kommer att se ett meddelande om att det här steget skriver över filer med samma namn som finns på servern. Klicka **[!UICONTROL Yes]** för att fortsätta.

>[!NOTE]
>
>Om du behöver överföra ytterligare filer för att slutföra [!DNL Repeater] uppgradering kommer Adobe att ge instruktioner om hur man gör detta.

När du har överfört uppgraderingsfilerna till [!DNL Repeater] maskin, [!DNL Repeater] startar automatiskt om sig själv och läser in den nya versionen.

## Uppgradera upprepning genom att kopiera filer {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Öppna uppgraderingsfilen från Adobe. Troligen är den här filen en [!DNL .zip] fil för uppgradering [!DNL Insight Server].
1. Gå till katalogen där du installerade [!DNL Repeater] (t.ex. [!DNL D:\Adobe\Repeater]).
1. Kopiera [!DNL bin] i [!DNL .zip] och klistra in den i [!DNL Repeater] installationskatalogen som skriver över befintlig [!DNL bin] mapp.

>[!NOTE]
>
>Om du behöver överföra ytterligare filer för att slutföra [!DNL Insight Server] uppgradering kommer Adobe att ge instruktioner om hur man gör detta.

När du har kopierat uppgraderingsfilerna till [!DNL Repeater] maskin, [!DNL Repeater] startar automatiskt om sig själv och läser in den nya versionen.
