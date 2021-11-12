---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: F94584BC-EC02-412D-B089-B98A6FF8F505
online version: ''
schema: 2.0.0
ms.openlocfilehash: b31483b37331e0ed7e4df78755dc6a1feeb98c74
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421564"
---
# New-AzureQuickVM

## SYNOPSIS
Mengonfigurasi dan membuat mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Windows (Default)
```
New-AzureQuickVM [-Windows] -ServiceName <String> [-Name <String>] -ImageName <String> [-Password <String>]
 [-ReverseDnsFqdn <String>] [-Location <String>] [-AffinityGroup <String>] [-AdminUsername <String>]
 [-Certificates <CertificateSettingList>] [-WaitForBoot] [-DisableWinRMHttps] [-EnableWinRMHttp]
 [-WinRMCertificate <X509Certificate2>] [-X509Certificates <X509Certificate2[]>] [-NoExportPrivateKey]
 [-NoWinRMEndpoint] [-VNetName <String>] [-SubnetNames <String[]>] [-DnsSettings <DnsServer[]>]
 [-HostCaching <String>] [-AvailabilitySetName <String>] [-InstanceSize <String>] [-MediaLocation <String>]
 [-DisableGuestAgent] [-CustomDataFile <String>] [-ReservedIPName <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Linux
```
New-AzureQuickVM [-Linux] -ServiceName <String> [-Name <String>] -ImageName <String> [-Password <String>]
 [-ReverseDnsFqdn <String>] [-Location <String>] [-AffinityGroup <String>] [-LinuxUser <String>] [-WaitForBoot]
 [-SSHPublicKeys <SSHPublicKeyList>] [-SSHKeyPairs <SSHKeyPairList>] [-VNetName <String>]
 [-SubnetNames <String[]>] [-DnsSettings <DnsServer[]>] [-HostCaching <String>] [-AvailabilitySetName <String>]
 [-InstanceSize <String>] [-MediaLocation <String>] [-DisableGuestAgent] [-CustomDataFile <String>]
 [-ReservedIPName <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureQuickVM** mengonfigurasi dan membuat mesin virtual Azure.
Cmdlet ini dapat menyebarkan mesin virtual ke layanan Azure yang sudah ada.
Cmdlet ini juga dapat membuat layanan Azure yang meng host mesin virtual baru.

## EXAMPLES

### Contoh 1: Membuat mesin virtual
```
PS C:\> New-AzureQuickVM -Windows -ServiceName "ContosoService17" -Name "VirutalMachine01" -ImageName "Image07" -Password "password" -AdminUsername "AdminMain" -WaitForBoot
```

Perintah ini akan membuat mesin virtual yang menjalankan sistem Windows operasi dalam layanan yang sudah ada.
Cmdlet mendasarkan mesin virtual pada gambar yang ditentukan.
Perintah menentukan parameter *WaitForBoot.*
Oleh karena itu, cmdlet menunggu mesin virtual untuk dimulai.

### Contoh 2: Membuat mesin virtual yang menggunakan sertifikat
```
PS C:\> $certs = Get-ChildItem Cert:\CurrentUser\My
PS C:\> New-AzureQuickVM -Windows -ServiceName "MySvc1" -name "MyWinVM1" -ImageName "Image07" -Password "password" -AdminUserName "AdminMain" -WinRMCertificate $certs[0] -X509Certificates $certs[1], $certs[2] -WaitForBoot
```

Perintah pertama mendapatkan sertifikat dari penyimpanan, dan menyimpannya dalam variabel $certs simpan.

Perintah kedua akan membuat mesin virtual yang menjalankan sistem Windows sistem operasi dalam layanan yang ada dari gambar.
Secara default, WinRM Https listener diaktifkan di komputer virtual.
Perintah menentukan parameter *WaitForBoot.*
Oleh karena itu, cmdlet menunggu mesin virtual untuk dimulai.
Perintah mengunggah Sertifikat WinRM dan X509Certificates ke layanan yang dihosting.

### Contoh 3: Buat mesin virtual yang menjalankan sistem operasi Linux
```
PS C:\> New-AzureQuickVM -Linux -ServiceName "ContosoServiceLinux01" -Name "LinuxVirtualMachine01" -ImageName "LinuxImage01" -LinuxUser "RootMain" -Password "password" -Location "Central US"
```

Perintah ini akan membuat mesin virtual yang menjalankan sistem operasi Linux dari gambar.
Perintah ini membuat layanan untuk menghosting mesin virtual baru.
Perintah menentukan lokasi untuk layanan tersebut.

### Contoh 4: Buat mesin virtual dan buat layanan untuk menghosting mesin virtual baru
```
PS C:\> $Locations = Get-AzureLocation
PS C:\> $Images = Get-AzureVMImage
PS C:\> New-AzureQuickVM -Windows -InstanceSize "Large" -ServiceName "ContosoService03" -Name " VirtualMachine25" -ImageName $images[4].imagename -Password "password" -AdminUsername "AdminMain" -Location $Locations[0].name
```

Perintah pertama mendapatkan lokasi menggunakan cmdlet **Get-AzureLocation,** lalu menyimpannya dalam $Locations larik.

Perintah kedua akan mendapatkan gambar yang tersedia menggunakan cmdlet **Get-AzureVMImage,** lalu menyimpannya dalam $Images array baru.

Perintah terakhir membuat mesin virtual besar bernama VirtualMachine25.
Mesin virtual menjalankan sistem Windows operasi.
Ini didasarkan pada salah satu gambar di $Images.
Perintah membuat layanan bernama ContosoService03 untuk komputer virtual baru.
Layanan berada di lokasi di $Locations.

### Contoh 5: Buat mesin virtual dengan nama IP khusus
```
PS C:\> $Locations = Get-AzureLocation
PS C:\> $Images = Get-AzureVMImage
PS C:\> New-AzureQuickVM -Windows -InstanceSize "Large" -ServiceName "ContosoService04" -Name "VirtualMachine27" -ImageName $Images[4].imagename -Password "password" -AdminUsername "AdminMain" -Location $Locations[0].name -ReservedIPName $ipName
```

Perintah pertama mendapatkan lokasi, lalu menyimpannya dalam $Locations array baru.

Perintah kedua akan mendapatkan gambar yang tersedia, lalu menyimpannya dalam $Images array tertentu.

Perintah terakhir membuat mesin virtual bernama VirtualMachine27 berdasarkan salah satu gambar di $Images.
Perintah membuat layanan di lokasi di $Locations.
Mesin virtual memiliki nama IP khusus, yang sebelumnya disimpan di $ipName khusus.

## PARAMETERS

### -AdminUsername
Menentukan nama pengguna akun Administrator yang dibuat cmdlet ini di komputer virtual.

```yaml
Type: String
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AffinityGroup
Menentukan grup affinity untuk komputer virtual.
Tentukan parameter ini atau parameter *Lokasi* hanya jika cmdlet ini membuat layanan Azure untuk mesin virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AvailabilitySetName
Menentukan nama kumpulan ketersediaan di mana cmdlet ini membuat mesin virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificates
Menentukan daftar sertifikat yang digunakan cmdlet untuk membuat layanan.

```yaml
Type: CertificateSettingList
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomDataFile
Menentukan file data untuk mesin virtual.
Cmdlet ini mengkodekan konten file sebagai Base64.
File tersebut harus kurang dari 64 kilobyte panjang.

Jika sistem operasi tamu adalah sistem Windows operasi, cmdlet ini menyimpan data ini sebagai file biner yang dinamai %SYSTEMDRIVE%\AzureData\CustomData.bin.

Jika sistem operasi tamu adalah Linux, cmdlet ini akan melewati data menggunakan file ovf-env.xml.
Penginstalan menyalin file tersebut ke direktori /var/lib/waagent.
Agen juga menyimpan data berkode Base64 di /var/lib/waagent/CustomData.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableGuestAgent
Cmdlet ini menonaktifkan infrastruktur sebagai agen tamu pengadaan layanan (IaaS).

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableWinRMHttps
Mengindikasikan bahwa cmdlet ini menonaktifkan Windows Manajemen Jarak Jauh (WinRM) di HTTPS.
Secara default, WinRM diaktifkan melalui HTTPS.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsSettings
Menentukan array objek server DNS yang menentukan pengaturan DNS untuk penyebaran baru.
Untuk membuat objek **DnsServer,** gunakan cmdlet **New-AzureDns.**

```yaml
Type: DnsServer[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableWinRMHttp
Menunjukkan bahwa cmdlet ini mengaktifkan WinRM melalui HTTP.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostCaching
Menentukan mode host cache untuk disk sistem operasi.
Nilai valid adalah: 

- ReadOnly
- ReadWrite

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageName
Menentukan nama gambar disk yang digunakan cmdlet ini untuk membuat disk sistem operasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceSize
Menentukan ukuran instans.
Nilai valid adalah: 

- ExtraSmall
- Kecil
- Sedang
- Besar
- ExtraLarge
- A5
- A6
- A7
- A8
- A9
- Basic_A0
- Basic_A1
- Basic_A2
- Basic_A3
- Basic_A4
- Standard_D1
- Standard_D2
- Standard_D3
- Standard_D4
- Standard_D11
- Standard_D12
- Standard_D13
- Standard_D14

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Linux
Mengindikasikan bahwa cmdlet ini membuat mesin virtual berbasis Linux.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxUser
Menentukan nama pengguna akun administratif Linux yang dibuat cmdlet ini di komputer virtual.

```yaml
Type: String
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan pusat data Azure yang menjadi host mesin virtual.
Jika Anda menetapkan parameter ini, cmdlet akan membuat layanan Azure di lokasi yang ditentukan.
Tentukan parameter ini atau *parameter AffinityGroup* hanya jika cmdlet ini membuat layanan Azure untuk komputer virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaLocation
Menentukan lokasi Azure Storage cmdlet ini yang membuat disk komputer virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama mesin virtual yang dibuat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoExportPrivateKey
Menunjukkan bahwa konfigurasi ini tidak mengunggah kunci privat.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWinRMEndpoint
Menunjukkan bahwa cmdlet ini tidak menambahkan titik akhir WinRM untuk komputer virtual.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Menentukan kata sandi untuk akun administratif.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReservedIPName
Menentukan nama IP khusus.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReverseDnsFqdn
Menentukan nama domain yang sepenuhnya memenuhi syarat untuk pencarian DNS terbalik.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Tentukan nama layanan Azure baru atau yang sudah ada, tempat cmdlet menambahkan mesin virtual baru.

Jika Anda menentukan layanan baru, cmdlet ini akan membuatnya.
Untuk membuat layanan baru, Anda harus menentukan parameter *Location* atau *AffinityGroup.*

Jika Anda menentukan layanan yang sudah ada, jangan tentukan *Location* atau *AffinityGroup*.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LINUXKeyPairs
Menentukan pasangan tombol LINUX.

```yaml
Type: SSHKeyPairList
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LINUXPublicKeys
Menentukan kunci publik KEYS.

```yaml
Type: SSHPublicKeyList
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetNames
Menentukan array nama subnet untuk komputer virtual.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VNetName
Menentukan nama jaringan virtual untuk komputer virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForBoot
Menunjukkan bahwa cmdlet ini menunggu mesin virtual untuk mencapai status ReadyRole.
Jika komputer virtual mencapai salah satu kondisi berikut ini, cmdlet gagal: FailedStartingVM, ProvisioningFailed, atau ProvisioningTimeout.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Windows
Mengindikasikan bahwa cmdlet ini membuat Windows virtual.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WinRMCertificate
Menentukan sertifikat bahwa cmdlet ini terkait ke titik akhir WinRM.

```yaml
Type: X509Certificate2
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -X509Certificates
Menentukan array sertifikat X509 yang digunakan untuk layanan yang dihosting.

```yaml
Type: X509Certificate2[]
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureLocation](./Get-AzureLocation.md)

[Get-AzureVMImage](./Get-AzureVMImage.md)

[AzureDn baru](./New-AzureDns.md)


