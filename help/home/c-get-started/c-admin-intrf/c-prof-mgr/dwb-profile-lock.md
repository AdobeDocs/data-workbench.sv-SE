---
description: Filen Internal.cfg som används i Profile Manager förhindrar att användare ändrar dina anpassade profiler med hjälp av hanterarna för profil, dimensioner, rapporter, arbetsytor, mått och filter.
title: Låsa profiler i arbetsstationen
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Låsa profiler i arbetsstationen{#locking-profiles-in-the-workstation}

Filen Internal.cfg som används i Profile Manager förhindrar att användare ändrar dina anpassade profiler med hjälp av hanterarna för profil, dimensioner, rapporter, arbetsytor, mått och filter.

Du kan förhindra att profilfiler ändras och skrivs över när du använder hanterarna genom att spara **[!DNL Internal.cfg]** filen i din anpassade profil i Profilhanteraren. Den här konfigurationsfilen förhindrar att användare skriver över flera filer när de arbetar i hanterarna (nås från menyn **Admin** > **Profil** ).

**Låsa profiler i profilhanteraren**

1. Högerklicka på **Admin** > **Profilhanteraren** på arbetsytan.

1. Högerklicka på **Profilhanteraren****[!DNL Context > Internal.cfg]** och **gör lokal**.

1. Högerklicka på bockmarkeringen i kolumnen **Användare** och spara i en `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Obs**: Det är bara chefernas ändringar av profilfiler som kan förhindras när de sparar **[!DNL Internal.cfg]** till en anpassad profil i Profilhanteraren. Du kan fortfarande spara arbetsytor på servern från skrivbordet med kommandot **Spara till server** .
