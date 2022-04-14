---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 9999E0EE-4A32-4C18-A6EC-2A073DC08710
online version: ''
schema: 2.0.0
ms.openlocfilehash: addc9aa0805d46cfaf2eeea9501ae85a93e79b6f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141880430"
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
Topik ini ditolak dan akan dihapus di masa mendatang.
Topik ini menjelaskan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mengetahui versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

Cmdlet **Remove-WAPackVMRole** menghapus objek peran mesin virtual.

## EXAMPLES

### Contoh 1: Hapus peran mesin virtual (yang dibuat menggunakan portal WAP)
```
PS C:\> $VMRole = Get-WAPackVMRole -Name "ContosoVMRole01"
PS C:\> Remove-WAPackVMRole -VMRole $VMRole
```

Perintah pertama mendapatkan peran mesin virtual bernama ContosoVMRole01 dengan menggunakan cmdlet **Get-WAPackVMRole** , lalu menyimpan objek tersebut dalam variabel $VMRole.

Perintah kedua menghapus peran mesin virtual yang disimpan di $VMRole.
Perintah meminta konfirmasi kepada Anda. Dengan asumsi peran mesin virtual ini dibuat menggunakan portal WAP, tidak perlu menentukan nama layanan awan.

### Contoh 2: Hapus peran mesin virtual yang dibuat setelah membuat layanan cloud secara manual
```
PS C:\> $VMRole = Get-WAPackVMRole -Name "ContosoVMRole02"
PS C:\> Remove-WAPackVMRole -VMRole $VMRole -CloudServiceName "ContosoCloudService02"
```

Perintah pertama mendapatkan peran mesin virtual bernama "ContosoVMRole02" dengan menggunakan cmdlet **Get-WAPackVMRole** , lalu menyimpan objek tersebut dalam variabel $VMRole.

Perintah kedua menghapus peran mesin virtual yang disimpan di $VMRole.
Perintah meminta konfirmasi kepada Anda.
Dengan asumsi peran mesin virtual ini tidak dibuat menggunakan portal, pengguna perlu menentukan nama layanan awan.
Dalam hal ini bernama "ContosoCloudService02".

### Contoh 3: Menghapus peran mesin virtual tanpa konfirmasi
```
PS C:\> $VMRole = Get-WAPackVMRole -Name "ContosoVMRole03"
PS C:\> Remove-WAPackVMRole -VMRole $VMRole -Force
```

Perintah pertama mendapatkan layanan awan bernama ContosoVMRole03 menggunakan cmdlet **Get-WAPackVMRole** , lalu menyimpan objek tersebut dalam variabel $VMRole.

Perintah kedua menghapus peran mesin virtual yang disimpan di $VMRole.
Perintah ini menyertakan parameter *Paksa* .
Perintah tidak meminta konfirmasi kepada Anda.

## PARAMETERS

### -CloudServiceName
Menentukan nama layanan cloud peran mesin virtual.

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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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
Mengembalikan objek yang mewakili item tempat Anda bekerja.
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

### -VMRole
Menentukan peran mesin virtual.
Untuk mendapatkan peran mesin virtual, gunakan cmdlet **Get-WAPackVMRole** .

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-WAPackVMRole](./Get-WAPackVMRole.md)

[New-WAPackVMRole](./New-WAPackVMRole.md)

[Set-WAPackVMRole](./Set-WAPackVMRole.md)


