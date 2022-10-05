---
description: Filen Internal.cfg som används i Profile Manager förhindrar att användare ändrar dina anpassade profiler av hanterarna för profil, Dimensioner, rapporter, arbetsytor, statistik och filter.
title: Låsa profiler i arbetsstationen
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
exl-id: 2604ceea-0e55-4ae7-a286-e5257e974a64
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# Låsa profiler i arbetsstationen{#locking-profiles-in-the-workstation}

{{eol}}

Filen Internal.cfg som används i Profile Manager förhindrar att användare ändrar dina anpassade profiler av hanterarna för profil, Dimensioner, rapporter, arbetsytor, statistik och filter.

Du kan förhindra att profilfiler ändras och skrivs över när du använder hanterarna genom att spara **[!DNL Internal.cfg]** till din anpassade profil i Profilhanteraren. Den här konfigurationsfilen förhindrar att användare skriver över flera filer när de arbetar i hanterarna (hämtas från **Administratör** > **Profil** meny).

**Låsa profiler i profilhanteraren**

1. Högerklicka på arbetsytan **Administratör** > **Profilhanteraren**.

1. I **Profilhanteraren**, högerklicka **[!DNL Context > Internal.cfg]** och **Gör lokal**.

1. Högerklicka på bockmarkeringen i **Användare** kolumn och spara i en `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Anteckning**: Det går endast att förhindra att chefer ändrar profilfiler när de sparar **[!DNL Internal.cfg]** till en anpassad profil i Profilhanteraren. Du kan fortfarande spara arbetsytor på servern från skrivbordet med hjälp av **Spara på server** -kommando.
