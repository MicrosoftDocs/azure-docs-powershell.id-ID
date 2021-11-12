---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 53BD6ED4-EA66-448B-8B18-F078C0738AF5
online version: ''
schema: 2.0.0
ms.openlocfilehash: 034303f0f3b92bbe15bc93c894e4b590e68709a7ff9ad715b93bd725923aa432
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419211"
---
# New-WAPackQuickVM

## SYNOPSIS
Membuat mesin virtual berdasarkan templat.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-WAPackQuickVM -Name <String> -Template <VMTemplate> -VMCredential <PSCredential>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell standar.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketikkan `(Get-Module -Name Azure).Version` .

Cmdlet **New-WAPackQuickVM** membuat mesin virtual berdasarkan templat.

## EXAMPLES

### Contoh 1: Membuat mesin virtual berdasarkan templat
```
PS C:\> $Credentials = Get-Credential
PS C:\> $TemplateId = Get-WAPackVMTemplate -Id 66242D17-189F-480D-87CF-8E1D749998C8
PS C:\> New-WAPackQuickVM -Name "VirtualMachine023" -Template $TemplateId -VMCredential $Credentials
```

Perintah pertama membuat objek **PSCredential,** lalu menyimpannya dalam $Credentials variabel.
Cmdlet meminta akun dan kata sandi Anda.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential` .

Perintah kedua mendapatkan templat menggunakan cmdlet **Get-WAPackVMTemplate.**
Perintah menentukan ID templat.
Perintah menyimpan objek templat di $TemplateID templat.

Perintah terakhir membuat mesin virtual bernama VirtualMachine023.
Perintah mendasarkan mesin virtual pada templat yang disimpan di $TemplateId.

## PARAMETERS

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
Untuk mendapatkan objek templat, gunakan cmdlet **Get-WAPackVMTemplate.**

```yaml
Type: VMTemplate
Parameter Sets: (All)
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
Parameter Sets: (All)
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

[New-WAPackvm](./New-WAPackVM.md)

[Get-WAPackvMTemplate](./Get-WAPackVMTemplate.md)


