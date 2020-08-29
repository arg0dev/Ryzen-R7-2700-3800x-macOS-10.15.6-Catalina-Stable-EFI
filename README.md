# Ryzen R7 2700/3800x-macOS-10.15.5/6 Catalina Stable

## Introduction

> Special EFI file for Zen architecture R7 processors between 2700x / 3800x

## System Features

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
  ### English Guide <br><br>
> ### OpenCore Update
</br>
<p style="font-size: 15px">With OpenCore 0.6.0, unlike previous versions, FwRuntimeService was removed and switched to OpenRuntime. In this context, I will tell you about this process scheme in order to make a fast and smooth transition from old versions to new versions.</p><br>

>First, download the <b><a href="https://github.com/acidanthera/OpenCorePkg/releases" target="_blank">OpenCore-0.6.0-RELEASE.zip</a></b> file from here.

>Extract the zip file you downloaded.

>Copy the <b>BOOTx64.efi</b> file to the <b>BOOT</b> folder in the <b>EFI</b> folder and paste it into the <b>EFI> BOOT</b> folder in the <b>EFI</b> partition you mounted.

>Paste the <b>OpenCore.efi</b> file found in <b>EFI> OC</b> to the EFI> OC folder in the <b>EFI</b> section you mounted.

>Rename the <b>OpenRuntime.efi</b> file in the <b>EFI> OC> Drivers</b> folder to <b>FwRuntimeService.efi</b> and paste it into the <b>EFI> OC></b> Drivers folder in the <b>EFI</b> section you connected.

>Otherwise, you'll get the <b>r11 required</b> error.

<br>

>### Important Notes
<br/>

><p style="font-size: 15px">The reason why the ALC887 model sound card, which I mentioned under the title of partially working hardware, is given under this title is that the microphone inputs are not working despite all the <b><a href="https://github.com/acidanthera/applealc/wiki/supported-codecs" target="_blank">layout-id</a></b>s. With <b>Apple ALC</b>, sound can be received natively over the speaker with all layout-ids.</p>


><p style="font-size: 15px">This is due to OpenCore. On the official documentation, it is stated that in AMD-based systems, layout-ids work smoothly in giving out sound, but the same situation does not exist in terms of microphones. Moreover, no kext has been developed to resolve this situation. For now, the solution to this problem is to use VoodooHDA.kext or a USB tip microphone. It is also stated that it will be developed in the future. You can examine it in detail <a href="https://dortania.github.io/OpenCore-Post-Install/universal/audio.html#no-mic-on-amd" target="_blank"><b>here</b></a>.</p>

><p style="font-size: 15px">Sleep/wake up problem has been eliminated on <b>SMBIOS</b> with <b>19.1</b> and <b>NVRAM> Special UUID> bootargs darkwake = 0</b> command.

><p style="font-size: 15px">In case you install with <b>EFI</b> file, remove <b>Misc> Security> Expose Sensitive Data</b> data if you do not own a <b>B450</b> motherboard.

><p style="font-size: 15px">The <b>EFI</b> file contains the most up-to-date kexts for the <b>TUF B450</b> AMD model. There is new update detection on <b>Hackintool</b>, but I do not recommend installing it because there are many users who receive <b>kernel panic</b> after the update of kexts such as <b>Lilu</b> and <b>WhateverGreen</b>.


><p style="font-size: 15px">If you have a problem with your keyboard on the <b>OpenCore BootLoader screen</b>, move the <b>PS2 drivers</b> in the <b>Drivers</b> folder in the <b>0.6.0</b> update file I gave above to the <b>EFI> OC> Drivers</b> folder in your memory and try again.

><p style="font-size: 15px">There are no problems with <b>AppStore</b> and <b>Apple applications.</b>

><p style="font-size: 15px">Also, thanks to this <b>EFI</b>, you can run your processor <b>stably</b> in <b>D.O.C.P</b> and <b>OC Tweak mode.<b/> <b>(TESTED OVER 3800x)</b>
  
### Turkish Guide <br><br>
> ### OpenCore Güncelleme
</br>
><p style="font-size: 15px">OpenCore 0.6.0 sürümü ile önceki sürümlerinden farklı olarak FwRuntimeService'i kullanımdan kaldırarak OpenRuntime'a geçiş yaptı. Bu bağlamda eski sürümlerden yeni sürümlere hızlı ve sorunsuz bir geçiş yapmak adına sizlere bu işlem tasarısından bahsedeceğim.</p><br>

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

