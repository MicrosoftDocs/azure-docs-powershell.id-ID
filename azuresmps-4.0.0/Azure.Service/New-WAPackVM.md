---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: AA7BD103-5C91-4E3B-9E46-2CAEDA5BA615
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0104aed9567bef851c8fa1c770f6798dddf58a5c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424115"
---
# New-WAPackVM

## SYNOPSIS
Membuat mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### CreateVMFromTemplate (Default)
```
New-WAPackVM -Name <String> -Template <VMTemplate> -VMCredential <PSCredential> [-VNet <VMNetwork>]
 [-ProductKey <String>] [-Windows] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### CreateLinuxvMFromTemplate
```
New-WAPackVM -Name <String> -Template <VMTemplate> -VMCredential <PSCredential> [-VNet <VMNetwork>] [-Linux]
 [-AdministratorSSHKey <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### CreateVMFromOSDisk
```
New-WAPackVM -Name <String> [-VNet <VMNetwork>] -OSDisk <VirtualHardDisk> -VMSizeProfile <HardwareProfile>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell ini.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketikkan `(Get-Module -Name Azure).Version` .

Cmdlet **New-WAPackvM** membuat mesin virtual.

## EXAMPLES

### Contoh 1: Membuat mesin virtual untuk Windows sistem operasi menggunakan templat
```
PS C:\> $Credentials = Get-Credential PS C:\> $Template = Get-WAPackVMTemplate -Name "ContosoTemplate04"PS C:\> New-WAPackVM -Name "ContosoV023" -Template $Template -VMCredential $Credentials -Windows
```

Perintah pertama membuat objek **PSCredential,** lalu menyimpannya dalam $Credentials variabel.
Cmdlet meminta akun dan kata sandi Anda.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential` .

Perintah kedua mendapatkan templat mesin virtual bernama ContosoTemplate04 dengan menggunakan cmdlet **Get-WAPackVMTemplate,** lalu menyimpannya dalam variabel $Template baru.

Perintah terakhir membuat mesin virtual bernama ContosoV023, berdasarkan templat yang disimpan di variabel $Template disimpan.
Perintah menentukan parameter *Windows,* dan, oleh karena itu, mesin virtual harus menjalankan versi sistem Windows operasi.

### Contoh 2: Buat mesin virtual untuk sistem operasi Linux menggunakan templat
```
PS C:\> $Credentials = Get-Credential
PS C:\> $Template = Get-WAPackVMTemplate -Name "ContosoTemplate19"
PS C:\> New-WAPackVM -Linux -Name "ContosoV028" -Template $Template -VMCredential $Credentials
```

Perintah pertama membuat objek **PSCredential,** lalu menyimpannya dalam $Credentials variabel.

Perintah kedua mendapatkan templat mesin virtual bernama ContosoTemplate19 dengan menggunakan cmdlet **Get-WAPackVMTemplate,** lalu menyimpannya dalam variabel $Template baru.

Perintah terakhir membuat mesin virtual bernama ContosoV028, berdasarkan templat yang disimpan di $Template variabel.
Perintah menentukan parameter *Linux,* dan oleh karena itu, mesin virtual harus menjalankan versi sistem operasi Linux.

### Contoh 3: Membuat mesin virtual dari disk sistem operasi dan profil ukuran
```
PS C:\> $OSDisk = Get-WAPackVMOSDisk -Name "ContosoDiskOS"
PS C:\> $SizeProfile = Get-WAPackVMSizeProfile -Name "MediumSizeVM"
PS C:\> New-WAPackVM -Name "ContosoV073" -OSDisk $OSDisk -VMSizeProfile $SizeProfile
```

Perintah pertama mendapatkan disk sistem operasi bernama ContosoDiskOS dengan menggunakan cmdlet **Get-WAPackVMOSDisk,** lalu menyimpannya di $OSDisk lokal.

Perintah kedua mendapatkan profil ukuran bernama MediumSizeVM dengan menggunakan cmdlet **Get-WAPackVMSizeProfile,** lalu menyimpannya dalam variabel $SizeProfile baru.

Perintah terakhir membuat mesin virtual bernama ContosoV073 dari disk sistem operasi yang disimpan di $OSDisk dan profil ukuran yang disimpan di $SizeProfile.

## PARAMETERS

### -AdministratorSSHKey
Menentukan kunci Secure Shell (SHELL) untuk akun Administrator.

```yaml
Type: String
Parameter Sets: CreateLinuxVMFromTemplate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Linux
Menunjukkan bahwa cmdlet membuat mesin virtual untuk menjalankan sistem operasi Linux.

```yaml
Type: SwitchParameter
Parameter Sets: CreateLinuxVMFromTemplate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama untuk mesin virtual.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OSDisk
Menentukan disk sistem operasi sebagai objek **Virtual DriveDisk.**
Untuk mendapatkan disk sistem operasi, gunakan cmdlet **Get-WAPackVMOSDisk.**

```yaml
Type: VirtualHardDisk
Parameter Sets: CreateVMFromOSDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductKey
Menentukan kunci produk.
Kunci produk adalah angka 25 digit yang mengidentifikasi lisensi produk.
Gunakan kunci produk untuk sistem operasi yang Anda rencanakan untuk diinstal di mesin virtual atau host.

```yaml
Type: String
Parameter Sets: CreateVMFromTemplate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Template
Menentukan templat.
Cmdlet membuat mesin virtual berdasarkan templat yang Anda tentukan.
Untuk mendapatkan objek templat, gunakan cmdlet Get-WAPackVMTemplate.

```yaml
Type: VMTemplate
Parameter Sets: CreateVMFromTemplate, CreateLinuxVMFromTemplate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMCredential
Menentukan kredensial untuk akun Administrator lokal.
Untuk mendapatkan objek **PSCredential,** gunakan cmdlet **Get-Credential.**
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential` .

```yaml
Type: PSCredential
Parameter Sets: CreateVMFromTemplate, CreateLinuxVMFromTemplate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMSizeProfile
Menentukan profil ukuran untuk komputer virtual sebagai objek **HardwareProfile.**
Untuk mendapatkan profil ukuran, gunakan cmdlet **Get-WAPackVMSizeProfile.**

```yaml
Type: HardwareProfile
Parameter Sets: CreateVMFromOSDisk
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VNet
Menentukan jaringan virtual.
Cmdlet menyambungkan mesin virtual ke jaringan virtual yang Anda tentukan.
Untuk mendapatkan jaringan virtual, gunakan cmdlet **Get-WAPackVNet.**

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Windows
Menunjukkan bahwa cmdlet membuat mesin virtual untuk menjalankan sistem Windows operasi.

```yaml
Type: SwitchParameter
Parameter Sets: CreateVMFromTemplate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-WAPackvm](./Get-WAPackVM.md)

[Remove-WAPackvm](./Remove-WAPackVM.md)

[Restart-WAPackvm](./Restart-WAPackVM.md)

[Resume-WAPackvm](./Resume-WAPackVM.md)

[Set-WAPackvm](./Set-WAPackVM.md)

[Start-WAPackvm](./Start-WAPackVM.md)

[Stop-WAPackvm](./Stop-WAPackVM.md)

[Suspend-WAPackvm](./Suspend-WAPackVM.md)

[Get-WAPackvMSizeProfile](./Get-WAPackVMSizeProfile.md)

[Get-WAPackvMTemplate](./Get-WAPackVMTemplate.md)

[Get-WAPackvMOSDisk](./Get-WAPackVMOSDisk.md)


