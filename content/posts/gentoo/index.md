+++
title = 'Měsíc s Gentoo'
date = 2024-05-16T20:43:32+02:00
tags = ["gentoo", "linux"]
+++


Měsíc zpátky, po další rozbité instalaci Windowsů, jsem se rozhodl pro instalaci další Linuxové distribuce. Chtěl jsem si zkusit něco nového, něco co jsem neznal. Do oka mi padlo Gentoo, řekl jsem si, že by mohlo být fajn, vystoupit z komfortní zóny. Ze studiiních důvodů, jsem nucen instalovat i Windows, jako dual-boot, o to bude tahle instalace zajímavější :D.

![gentoo neofetch](/img/neofetch.png)

## První pokus o instalaci

Začal jsem tak, jak začínám každou reinstalaci. Dokumenty a další soubory z hlavního disku jsem překopíroval na vedlejší a započal jsem instalaci. Jak se správně dělá, prvně jsem začal instalovat Windows. Ta proběhla bez větších komplikací, a během 20 minut jsem byl na ploše, a začal jsem instalovat drivery. Po instalaci jsem ale zjistil nemilou věc, Windows, jako první nainstalovaný systém, si udělal EFI partition o velikosti 200MB. Rád si držím na disku pořádek, a to i v partitionách, tím pádem intrid a kernel ukládám také na EFI partition, o které jsem se bál, že je moc malá. Nadešel čas na druhou instalaci.

## Druý pokus o instalaci

Poučen, jsem instalačku nabootoval znovu, našel jsem článek na [ArchWiki](https://wiki.archlinux.org/title/Dual_boot_with_Windows#The_EFI_system_partition_created_by_Windows_Setup_is_too_small) a pustil jsem se na věc. A opravdu se povedlo! Za dalšich 20 minut jsem byl opět na ploše, tentokrát již s EFI partition velkou 1GB. Po instalaci driverů a pár dalších programů jsem se pustil do instalace Gentoo.

### Instalace Gentoo

Instalace Gentoo probíhá hodně podobně, jako instalace Arch Linuxu, se kterým už mám více zkušeností. Ze začátku jsem si všimnul, že [Gentoo Handbook](https://wiki.gentoo.org/wiki/Handbook:Main_Page) je o hodně jednodužší a podrobnější (ano, paradox 😄) než návod na instalaci pro ArchLinux. Instalace proběhla opět, bez větších kompikací, během pár hodin jsem byl v TTY,s plně funkčním systémem.

### Gentoo Handbook - a proč si myslím že je lepší než ArchWiki?

Jak už jsem zmiňoval, [Gentoo Handbook](https://wiki.gentoo.org/wiki/Handbook:Main_Page) - obdoba ArchLinux Install Guide pro Gentoo, je z mého pohledu jak více podrobná, tak i jednodužší. Je to paradox, ale nechte mě to vysvětlit. Gentoo Handbook, není jen takový malý, stručný návod na instalaci systému. Po přečtení, budete chápat a vědět co všechno vlastně běží na vašem systému, u většiny rozhodnutí máte více vysvětlených možností, ať už je to u vašeho sys loggeru, ale taky třeba u instalace bootloaderu. Gentoo Handbook provede uživatele i přesně tím jaký si má udělat partition scheme, i když by vpodstatě nemusel. Arch Install Guide není špatný, má svojí funkci a tu zvládá, ale myslím si, že kdyby nováčci na Arch Linuxu měli stejnou podrobnost a stejné "vedení za ručičku" jako u Gentoo Handbook, nebyl by potřeba ani archinstall script.

## První Problém - NVidia GPU

Narážíme na první problém, NVidia. NVidia grafiky jsou na Linuxu celkem ošemetné. Můj notebook podporuje NVidia Optimus, to znamená, že dokáže vypínat a přepínat mezi iGPU (integrovaná grafická karta) a dGPU (dedikovaná grafická karta). To se mi na OpenRC bohužel nepodařilo ruzfungovat.

Řešení? prime-run

Utilitka prime-run umožňuje spouštět aplikace za pomocí dGPU, bez nutného přepnutí celé grafiky. Tím pádem XFCE běží na iGPU a hra, popřípadně třeba GIMP zase na dGPU, po instalaci prime-run vše fungovalo bez problému a svůj problém, prozatím jediný na který jsem narazil, byl vyřešen.

## Moje konfigurace

Teď už na ty zábavné věci. Tohle je moje stávajíci konfigurace:

![gentoo busy](/img/busy.png)

Jako svůj DE používám XFCE s tématem Catpuccin. Jako terminál používám alacritty a dock dole je Plank.

## A mělo to vlastně celé cenu?

Z praktického hlediska, asi ne = počítač by byl stejně použitelný i na jakékoli jiné distribuci. Ale z toho jak to cítím já, si myslím že switch na Gentoo byl dobrý nápad. Chtěl jsem si vyzkoušet něco nového, zároveň jsem si chtěl denně používá OS, který neběží na SystemD (i když proti němu nic nemám). S tím že nemám pomalý počítač, se běžná aktualizace balíků (s vyjímkou LibreOffice a Firefoxu) dá zvládnout pod 10 minut. Na Gentoo jsem spokojený, můj systém je stabilní a nemám v plánu se posouvat někam dál.

Díky za přečtení!

~ Vítek 👋
