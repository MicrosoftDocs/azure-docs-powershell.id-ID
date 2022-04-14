---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: F94584BC-EC02-412D-B089-B98A6FF8F505
online version: ''
schema: 2.0.0
ms.openlocfilehash: b31483b37331e0ed7e4df78755dc6a1feeb98c74
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141816562"
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
Cmdlet ini dapat membuat layanan Azure alternatif yang menghosting mesin virtual baru.

## EXAMPLES

### Contoh 1: Membuat mesin virtual
```
PS C:\> New-AzureQuickVM -Windows -ServiceName "ContosoService17" -Name "VirutalMachine01" -ImageName "Image07" -Password "password" -AdminUsername "AdminMain" -WaitForBoot
```

Perintah ini membuat mesin virtual yang menjalankan sistem operasi Windows dalam layanan yang sudah ada.
Cmdlet mendasarkan mesin virtual pada gambar yang ditentukan.
Perintah menentukan parameter *WaitForBoot* .
Oleh karena itu, cmdlet menunggu mesin virtual dimulai.

### Contoh 2: Membuat mesin virtual yang menggunakan sertifikat
```
PS C:\> $certs = Get-ChildItem Cert:\CurrentUser\My
PS C:\> New-AzureQuickVM -Windows -ServiceName "MySvc1" -name "MyWinVM1" -ImageName "Image07" -Password "password" -AdminUserName "AdminMain" -WinRMCertificate $certs[0] -X509Certificates $certs[1], $certs[2] -WaitForBoot
```

Perintah pertama mendapatkan sertifikat dari toko, dan menyimpannya dalam variabel $certs.

Perintah kedua membuat mesin virtual yang menjalankan sistem operasi Windows dalam layanan yang sudah ada dari gambar.
Secara default, pendengar WinRM Https diaktifkan di mesin virtual.
Perintah menentukan parameter *WaitForBoot* .
Oleh karena itu, cmdlet menunggu mesin virtual dimulai.
Perintah mengunggah Sertifikat WinRM dan X509Menerima ke layanan yang dihosting.

### Contoh 3: Membuat mesin virtual yang menjalankan sistem operasi Linux
```
PS C:\> New-AzureQuickVM -Linux -ServiceName "ContosoServiceLinux01" -Name "LinuxVirtualMachine01" -ImageName "LinuxImage01" -LinuxUser "RootMain" -Password "password" -Location "Central US"
```

Perintah ini membuat mesin virtual yang menjalankan sistem operasi Linux dari gambar.
Perintah ini membuat layanan untuk menghosting mesin virtual baru.
Perintah menentukan lokasi untuk layanan.

### Contoh 4: Buat mesin virtual dan buat layanan untuk menghosting mesin virtual baru
```
PS C:\> $Locations = Get-AzureLocation
PS C:\> $Images = Get-AzureVMImage
PS C:\> New-AzureQuickVM -Windows -InstanceSize "Large" -ServiceName "ContosoService03" -Name " VirtualMachine25" -ImageName $images[4].imagename -Password "password" -AdminUsername "AdminMain" -Location $Locations[0].name
```

Perintah pertama mendapatkan lokasi dengan menggunakan cmdlet **Get-AzureLocation** , lalu menyimpannya dalam variabel array $Locations.

Perintah kedua mendapatkan gambar yang tersedia menggunakan cmdlet **Get-AzureVMImage** , lalu menyimpannya dalam variabel array $Images.

Perintah terakhir membuat mesin virtual besar bernama VirtualMachine25.
Mesin virtual menjalankan sistem operasi Windows.
Ini didasarkan pada salah satu gambar di $Images.
Perintah membuat layanan bernama ContosoService03 untuk mesin virtual baru.
Layanan berada di lokasi di $Locations.

### Contoh 5: Membuat mesin virtual yang memiliki nama IP khusus
```
PS C:\> $Locations = Get-AzureLocation
PS C:\> $Images = Get-AzureVMImage
PS C:\> New-AzureQuickVM -Windows -InstanceSize "Large" -ServiceName "ContosoService04" -Name "VirtualMachine27" -ImageName $Images[4].imagename -Password "password" -AdminUsername "AdminMain" -Location $Locations[0].name -ReservedIPName $ipName
```

Perintah pertama mendapatkan lokasi, lalu menyimpannya dalam variabel array $Locations.

Perintah kedua mendapatkan gambar yang tersedia, lalu menyimpannya dalam variabel array $Images.

Perintah terakhir membuat mesin virtual bernama VirtualMachine27 berdasarkan salah satu gambar dalam $Images.
Perintah membuat layanan di lokasi di $Locations.
Mesin virtual memiliki nama IP khusus, sebelumnya disimpan dalam variabel $ipName.

## PARAMETERS

### -AdminUsername
Menentukan nama pengguna akun Administrator yang dibuat cmdlet ini pada mesin virtual.

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
Menentukan grup affinity untuk mesin virtual.
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
Menentukan nama set ketersediaan di mana cmdlet ini membuat mesin virtual.

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

### -Sertifikat
Menentukan daftar sertifikat yang digunakan cmdlet ini untuk membuat layanan.

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
Panjang file harus kurang dari 64 kilobyte.

Jika sistem operasi tamu adalah sistem operasi Windows, cmdlet ini menyimpan data ini sebagai file biner yang bernama %SYSTEMDRIVE%\AzureData\CustomData.bin.

Jika sistem operasi tamu adalah Linux, cmdlet ini melewati data menggunakan file ovf-env.xml.
Instalasi menyalin file tersebut ke direktori /var/lib/waagent.
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
Menunjukkan bahwa cmdlet ini menonaktifkan infrastruktur sebagai layanan (IaaS) penyediaan agen tamu.

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
Menunjukkan bahwa cmdlet ini menonaktifkan Windows Remote Management (WinRM) di HTTPS.
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
Untuk membuat objek **DnsServer** , gunakan cmdlet **New-AzureDns** .

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
Menentukan mode cache host untuk disk sistem operasi.
Nilai yang valid adalah: 

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
Menentukan nama citra disk yang digunakan cmdlet ini untuk membuat disk sistem operasi.

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
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

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

### -Instancesize
Menentukan ukuran instans.
Nilai yang valid adalah: 

- ExtraSmall
- Kecil
- Menengah
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
Menunjukkan bahwa cmdlet ini membuat mesin virtual berbasis Linux.

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
Menentukan nama pengguna akun administratif Linux yang dibuat cmdlet ini di mesin virtual.

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
Jika Anda menentukan parameter ini, cmdlet akan membuat layanan Azure di lokasi yang ditentukan.
Tentukan parameter ini atau parameter *AffinityGroup* hanya jika cmdlet ini membuat layanan Azure untuk mesin virtual.

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

### -MediaLokasi
Menentukan lokasi Azure Storage tempat cmdlet ini membuat disk mesin virtual.

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
Menunjukkan bahwa cmdlet ini tidak menambahkan titik akhir WinRM untuk mesin virtual.

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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Menentukan nama layanan Azure baru atau yang sudah ada tempat cmdlet ini menambahkan mesin virtual baru.

Jika Anda menentukan layanan baru, cmdlet ini akan membuatnya.
Untuk membuat layanan baru, Anda harus menentukan parameter *Lokasi* atau *AffinityGroup* .

Jika Anda menentukan layanan yang sudah ada, jangan tentukan *Lokasi* atau *AffinityGroup*.

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

### -SSHKeyPairs
Menentukan pasangan kunci SSH.

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

### -SSHPublicKeys
Menentukan kunci publik SSH.

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
Menentukan array nama subnet untuk mesin virtual.

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
Menentukan nama jaringan virtual untuk mesin maya.

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
Menunjukkan bahwa cmdlet ini menunggu mesin virtual mencapai ReadyRole negara bagian.
Jika mesin virtual mencapai salah satu status berikut, cmdlet gagal: FailedStartingVM, ProvisioningFailed, atau ProvisioningTimeout.

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
Menunjukkan bahwa cmdlet ini membuat mesin virtual Windows.

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
Menentukan sertifikat yang dikaitkan cmdlet ini ke titik akhir WinRM.

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

### -X509Sertifikaat
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureLocation](./Get-AzureLocation.md)

[Get-AzureVMImage](./Get-AzureVMImage.md)

[AzureDns baru](./New-AzureDns.md)


