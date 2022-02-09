---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/new-azkeyvaultroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/New-AzKeyVaultRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/New-AzKeyVaultRoleDefinition.md
ms.openlocfilehash: 9edb8d250d1bd2c48790127638da2795ae77ebd8
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138305804"
---
# New-AzKeyVaultRoleDefinition

## SYNOPSIS
Membuat definisi peran kustom di HSM.

## SYNTAX

### InputObject (Default)
```
New-AzKeyVaultRoleDefinition [-HsmName] <String> [-Scope <String>] [-Role] <PSKeyVaultRoleDefinition>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputFile
```
New-AzKeyVaultRoleDefinition [-HsmName] <String> [-Scope <String>] [-InputFile] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet `New-AzKeyVaultRoleDefinition` membuat peran kustom dalam Azure Role-Based Access Control dari HSM yang dikelola Azure KeyVault.

Sediakan file definisi peran JSON atau objek `PSKeyVaultRoleDefinition` sebagai input.
Pertama, gunakan perintah `Get-AzKeyVaultRoleDefinition` untuk menghasilkan objek definisi peran garis dasar.
Lalu, modifikasi propertinya sebagaimana diperlukan.
Terakhir, gunakan perintah ini untuk membuat peran kustom menggunakan definisi peran.

## EXAMPLES

### Contoh 1
```powershell
$role = Get-AzKeyVaultRoleDefinition -HsmName myHsm -RoleDefinitionName 'Managed HSM Crypto User'
$role.Name = $null
$role.RoleName = "my custom role"
$role.Description = "description for my role"
$role.Permissions[0].DataActions = @("Microsoft.KeyVault/managedHsm/roleAssignments/write/action", "Microsoft.KeyVault/managedHsm/roleAssignments/delete/action") # todo
New-AzKeyVaultRoleDefinition -HsmName myHsm -Role $role
```

Contoh ini menggunakan peran "Pengguna Crypto HSM Terkelola" yang telah ditentukan sebelumnya sebagai templat untuk membuat peran kustom.

### Contoh 2
```powershell
Get-AzKeyVaultRoleDefinition -HsmName myHsm -RoleDefinitionName 'Managed HSM Crypto User' | ConvertTo-Json -Depth 9 > C:\Temp\roleDefinition.json
# Edit roleDefinition.json. Make sure to clear "Name" so as not to overwrite an existing role.
New-AzKeyVaultRoleDefinition -HsmName myHsm -InputFile C:\Temp\roleDefinition.json
```

Contoh ini menggunakan file JSON sebagai input peran kustom.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HsmName
Nama HSM.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputFile
Nama file berisi definisi peran tunggal.

```yaml
Type: System.String
Parameter Sets: InputFile
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Peran
Objek definisi peran.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleDefinition
Parameter Sets: InputObject
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Lingkup di mana penetapan peran atau definisi berlaku, misalnya '/' atau '/keys' atau '/keys/{keyName}'.
'/' digunakan ketika dihilangkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleDefinition

## CATATAN

## RELATED LINKS
