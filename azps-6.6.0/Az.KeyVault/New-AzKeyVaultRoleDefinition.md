---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/new-azkeyvaultroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/New-AzKeyVaultRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/New-AzKeyVaultRoleDefinition.md
ms.openlocfilehash: 6ebab8bd07d570a5d55d95e48d7b71017396148e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141911631"
---
# New-AzKeyVaultRoleDefinition

## SYNOPSIS
Membuat definisi peran kustom pada HSM.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/new-azkeyvaultroledefinition) untuk informasi terbaru.

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
`New-AzKeyVaultRoleDefinition` Cmdlet membuat peran kustom di Azure Role-Based Access Control dari HSM yang dikelola Azure KeyVault.

Menyediakan file definisi peran JSON atau `PSKeyVaultRoleDefinition` objek sebagai input.
Pertama, gunakan `Get-AzKeyVaultRoleDefinition` perintah untuk menghasilkan objek definisi peran garis dasar.
Lalu, ubah propertinya sesuai kebutuhan.
Terakhir, gunakan perintah ini untuk membuat peran kustom menggunakan definisi peran.

## EXAMPLES

### Contoh 1
```powershell
$role = Get-AzKeyVaultRoleDefinition -HsmName myHsm -RoleDefinitionName 'Managed HSM Crypto User'
$role.Name = $null
$role.RoleName = "my custom role"
$role.Description = "description for my role"
$role.Permissions[0].AllowedDataActions = @("Microsoft.KeyVault/managedHsm/roleAssignments/write/action", "Microsoft.KeyVault/managedHsm/roleAssignments/delete/action")
New-AzKeyVaultRoleDefinition -HsmName myHsm -Role $role
```

Contoh ini menggunakan peran "Pengguna Kripto HSM Terkelola" yang sudah ditentukan sebelumnya sebagai templat untuk membuat peran kustom.

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
Nama file yang berisi definisi peran tunggal.

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
Lingkup tempat penetapan peran atau definisi diterapkan, misalnya '/' atau '/keys' atau '/keys/{keyName}'.
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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleDefinition

## CATATAN

## RELATED LINKS
