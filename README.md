# Ryzen R7 2700/3800x-macOS-10.15.5 Catalina Stable-EFI

## Introduction

> Special EFI file for Zen architecture R7 processors between 2700x / 3800x

## System Features

<br>

>### AMD Based Custom System <br><br>

>Asus TUF B450-Plus Gaming (3 PCI-E x1, 2 PCI-E x16, 1 M.2, 4 DDR4 DIMM, Audio, Video, Gigabit LAN) 

>OctalCore AMD Ryzen 7 3800X, 4300 MHz (43 x 100) 36MB Cache Soket AM4 

>Radeon RX 580 Series (8 GB) 

>Realtek ALC887 @ AMD K17.7 - High Definition Audio Controller 

>Realtek PCIe GbE Family Controller 

>Samsung SSD 860 EVO 500GB (500 GB, SATA-III)

>ST2000DM008-2FR102 (2 TB, 5000 RPM, SATA-III)

>GSKILL 16GB (2x8GB) Flare X DDR4 3200MHz CL16 1.35V Dual Kit Ram

>JAMESDONKEY JD120 120GB

## Installation

#### <p style="color: #828282;">Turkish Guide</p><br>
> ### OpenCore Güncelleme
</br>
<p style="font-size: 15px">OpenCore 0.6.0 sürümü ile önceki sürümlerinden farklı olarak FwRuntimeService'i kullanımdan kaldırarak OpenRuntime'a geçiş yaptı. Bu bağlamda eski sürümlerden yeni sürümler hızlı ve sorunsuz bir geçiş yapmak adına sizlere bu işlem tasarısından bahsedeceğim.</p><br>

> Öncelikle buradan <b><a href="https://github.com/acidanthera/OpenCorePkg/releases" target="_blank">OpenCore-0.6.0-RELEASE.zip</a></b> dosyasını indirin.

>İndirdiğiniz zip dosyasını çıkartın.

><b>EFI</b> klasörü içerisinde bulunan <b>BOOT</b> klasörü içerisindeki <b>BOOTx64.efi</b> dosyasını kopyalayıp mount ettiğiniz <b>EFI</b> bölümü içerisindeki <b>EFI>BOOT </b> klasörü içerisine yapıştırın.

>EFI klasörü içerisinde bulunan OC klasörü içerisindeki OpenCore.efi dosyasını mount ettiğiniz EFI bölümü içerisindeki EFI>OC klasörü içerisine yapıştırın.

><b>EFI > OC > Drivers </b>klasörü içerisinde bulunan <b>OpenRuntime.efi</b> dosyasının adını <b>FwRuntimeService.efi </b>olarak değiştirip mount ettiğiniz EFI bölümü içerisindeki <b>EFI > OC > Drivers</b> klasörü içerisine yapıştırın. 

>Aksi halde <b>r11 required</b> hatası alacaksınız.

<br>

>### Önemli Notlar
<br/>

><p style="font-size: 15px">Kısmi çalışan donanımlar başlığı altında belirttiğim <b>ALC887</b> model ses kartının bu başlık altında verilmesinin nedeni mikrofon girişlerinin tüm <b><a href="https://github.com/acidanthera/applealc/wiki/supported-codecs" target="_blank">layout-id</a></b>'lerin denenmesine rağmen çalışmıyor olmasıdır. <b>Apple ALC</b> ile <b>native</b> olarak hoparlör üzerinden tüm <b>layout-id</b>'ler ile ses alınabilmektedir.</p>

><p style="font-size: 15px">Bu durum <b>OpenCore</b>'dan kaynaklanmaktadır. 
>Resmi dökümantasyonu üzerinde  <b>AMD</b> tabanlı sistemlerde layout-id'lerin dışarı ses verme konusunda sorunsuz çalıştığı fakat mikrofon konusunda aynı durumun mevcut olmadığı belirtilmektedir. Üstelik bu durumun çözümlenmesi adına herhangi bir kext geliştirilmedi. Şu an için bu sorunun çözümü <b>VoodooHDA.kext</b> ya da <b>USB</b> uçlu mikrofon kullanmak. İlerleyen süreçlerde geliştirileceği de ayrıca belirtilmektedir. <a href="https://dortania.github.io/OpenCore-Post-Install/universal/audio.html#no-mic-on-amd" target="_blank"><b>Buradan</b></a> detaylı bir şekilde inceleyebilirsiniz.</p>

><p style="font-size: 15px">Ek içeriğinde paylaşmış olduğum <b>EFI</b> dosyası <b>Asus TUF B450</b> AMD mimari mobolar için <b>R7 2700(X)</b> serisinden <b>3800(X)</b>serisine kadar sorunsuz kurulum desteği sunmaktadır.

><p style="font-size: 15px"><b>Sleep/wake up</b> problemi <b>SMBIOS</b> üzerinde <b>19,1</b> ve <b>NVRAM > Özel UUID > bootargs darkwake=0</b> komutu ile ortadan kaldırılmıştır.

><p style="font-size: 15px"><b>EFI</b> dosyası ile kurulum yapmanız halinde <b>Misc > Security > Expose Sensitive Data</b> verisini <b>B450</b> model bir anakart sahibi değilseniz kaldırın.

><p style="font-size: 15px"><b>EFI</b> dosyası TUF B450 AMD mobosu için içerisinde en güncel kextleri barındırmaktadır. <b>Hackintool</b> üzerinde yeni güncelleme tespiti bulunmaktadır lakin kurulumunu önermiyorum zira <b>Lilu</b> ve <b>WhateverGreen</b> gibi kextlerin update işlemi sonrası <b>kernel panic</b> alan birçok kullanıcı bulunuyor.

><p style="font-size: 15px"><b>OpenCore BootLoader </b> ekranında klavyenizde sorun yaşamanız halinde yukarıda vermiş olduğum <b>0.6.0</b> güncelleme dosyasında bulunan <b>Drivers</b> klasöründeki <b>PS2</b> sürücülerini belleğinizde bulunan <b>EFI > OC > Drivers</b> klasörüne taşıyıp yeniden deneyin.

><p style="font-size: 15px"><b>AppStore</b> ve <b>Apple uygulamaları</b> ile alakalı hiçbir sorun bulunmamaktadır.

><p style="font-size: 15px">Ayrıca bu <b>EFI</b> sayesinde <b>D.O.C.P</b> ve <b>OC Tweak</b> modunda stabil bir şekilde işlemcinizi çalıştırabilirsiniz. <b style="color: green;">(3800x ÜZERİNDE TEST EDİLDİ)</b>
