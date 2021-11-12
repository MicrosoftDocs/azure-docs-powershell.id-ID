---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 9999E0EE-4A32-4C18-A6EC-2A073DC08710
online version: ''
schema: 2.0.0
ms.openlocfilehash: addc9aa0805d46cfaf2eeea9501ae85a93e79b6f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422467"
---
# Remove-WAPackVMRole

## SYNOPSIS
Menghapus objek peran mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### FromVMRoleObject (Default)
```
Remove-WAPackVMRole -VMRole <VMRole> [-PassThru] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FromCloudService
```
Remove-WAPackVMRole -VMRole <VMRole> -CloudServiceName <String> [-PassThru] [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Remove-WAPackVMRole** menghapus objek peran mesin virtual.

## EXAMPLES

### Contoh 1: Menghapus peran mesin virtual (yang dibuat menggunakan portal WAP)
```
PS C:\> $VMRole = Get-WAPackVMRole -Name "ContosoVMRole01"
PS C:\> Remove-WAPackVMRole -VMRole $VMRole
```

Perintah pertama mendapatkan peran mesin virtual bernama ContosoVMRole01 dengan menggunakan cmdlet **Get-WAPackVMRole,** lalu menyimpan objek tersebut dalam $VMRole variabel.

Perintah kedua menghapus peran mesin virtual yang disimpan di $VMRole.
Perintah akan meminta konfirmasi Anda. Dengan menganggap peran mesin virtual ini dibuat menggunakan portal WAP, Anda tidak perlu menentukan nama layanan awan.

### Contoh 2: Menghapus peran mesin virtual yang dibuat setelah membuat layanan awan secara manual
```
PS C:\> $VMRole = Get-WAPackVMRole -Name "ContosoVMRole02"
PS C:\> Remove-WAPackVMRole -VMRole $VMRole -CloudServiceName "ContosoCloudService02"
```

Perintah pertama mendapatkan peran mesin virtual bernama "ContosoVMRole02" dengan menggunakan cmdlet **Get-WAPackVMRole,** lalu menyimpan objek tersebut dalam $VMRole variabel.

Perintah kedua menghapus peran mesin virtual yang disimpan di $VMRole.
Perintah akan meminta konfirmasi Anda.
Dengan menganggap peran mesin virtual ini tidak dibuat menggunakan portal, pengguna harus menentukan nama layanan awan.
Dalam hal ini dinamai "ContosoCloudService02".

### Contoh 3: Menghapus peran mesin virtual tanpa konfirmasi
```
PS C:\> $VMRole = Get-WAPackVMRole -Name "ContosoVMRole03"
PS C:\> Remove-WAPackVMRole -VMRole $VMRole -Force
```

Perintah pertama mendapatkan layanan awan bernama ContosoVMRole03 dengan menggunakan cmdlet **Get-WAPackVMRole,** lalu menyimpan objek tersebut di $VMRole variabel.

Perintah kedua menghapus peran mesin virtual yang disimpan di $VMRole.
Perintah ini menyertakan parameter *Force.*
Perintah tidak akan meminta konfirmasi Anda.

## PARAMETERS

### -CloudServiceName
Menentukan nama layanan awan dari peran mesin virtual.

```yaml
Type: String
Parameter Sets: FromCloudService
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -PassThru
Mengembalikan objek yang mewakili item yang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### -VMRole
Menentukan peran mesin virtual.
Untuk mendapatkan peran mesin virtual, gunakan cmdlet **Get-WAPackVMRole.**

```yaml
Type: VMRole
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-WAPackVMRole](./Get-WAPackVMRole.md)

[New-WAPackVMRole](./New-WAPackVMRole.md)

[Set-WAPackvMRole](./Set-WAPackVMRole.md)


