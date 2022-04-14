---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 53BD6ED4-EA66-448B-8B18-F078C0738AF5
online version: ''
schema: 2.0.0
ms.openlocfilehash: ba9692f77e2a53d96db0567f6e480009b4403046
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142094130"
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
Topik ini ditolak dan akan dihapus di masa mendatang.
Topik ini menjelaskan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mengetahui versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

Cmdlet **New-WAPackQuickVM** membuat mesin virtual berdasarkan templat.

## EXAMPLES

### Contoh 1: Membuat mesin virtual berdasarkan templat
```
PS C:\> $Credentials = Get-Credential
PS C:\> $TemplateId = Get-WAPackVMTemplate -Id 66242D17-189F-480D-87CF-8E1D749998C8
PS C:\> New-WAPackQuickVM -Name "VirtualMachine023" -Template $TemplateId -VMCredential $Credentials
```

Perintah pertama membuat objek **PSCredential** , lalu menyimpannya dalam variabel $Credentials.
Cmdlet meminta anda untuk akun dan kata sandi.
Untuk informasi selengkapnya, ketik .`Get-Help Get-Credential`

Perintah kedua mendapatkan templat dengan menggunakan cmdlet **Get-WAPackVMTemplate** .
Perintah menentukan ID templat.
Perintah menyimpan objek templat dalam variabel $TemplateID.

Perintah terakhir membuat mesin virtual bernama VirtualMachine023.
Perintah mendasarkan mesin virtual pada templat yang disimpan di $TemplateId.

## PARAMETERS

### -Nama
Menentukan nama untuk mesin maya.

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

### -Templat
Menentukan templat.
Cmdlet membuat mesin virtual berdasarkan templat yang Anda tentukan.
Untuk mendapatkan objek templat, gunakan cmdlet **Get-WAPackVMTemplate** .

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
Untuk mendapatkan objek **PSCredential** , gunakan cmdlet **Get-Credential** .
Untuk informasi selengkapnya, ketik .`Get-Help Get-Credential`

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[WAPackVM Baru](./New-WAPackVM.md)

[Get-WAPackVMTemplate](./Get-WAPackVMTemplate.md)


