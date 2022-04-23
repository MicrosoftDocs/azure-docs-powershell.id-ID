---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/remove-azkeyvaultroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultRoleDefinition.md
ms.openlocfilehash: ff21ddcfec7bbef0be4314f308fee6c00eab2a3a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143285093"
---
# Remove-AzKeyVaultRoleDefinition

## SYNOPSIS
Menghapus definisi peran kustom dari HSM.

## SYNTAX

### ByName (Default)
```
Remove-AzKeyVaultRoleDefinition [-HsmName] <String> [-Scope <String>] -RoleName <String> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-AzKeyVaultRoleDefinition [-HsmName] <String> [-Scope <String>] -InputObject <PSKeyVaultRoleDefinition>
 [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
`Remove-AzKeyVaultRoleDefinition` Cmdlet menghapus peran kustom di Azure Role-Based Access Control Azure KeyVault yang dikelola HSM.
`-RoleName` Berikan parameter peran kustom atau objek peran yang sudah ada untuk menghapus peran kustom tersebut.
Secara default, `Remove-AzKeyVaultRoleDefinition` meminta konfirmasi kepada Anda.
Untuk menyembunyikan perintah, gunakan `-Force` parameter.

## EXAMPLES

### Contoh 1

```powershell
Remove-AzKeyVaultRoleDefinition -HsmName myHsm -RoleName "my role"
```

Contoh ini menghapus peran kustom bernama "peran saya".

### Contoh 2

```powershell
$role = Get-AzKeyVaultRoleDefinition -HsmName myHsm -RoleName "my role"
$role | Remove-AzKeyVaultRoleDefinition -HsmName myHsm -Force
```

Contoh ini menghapus peran kustom bernama "peran saya" dengan mempipa objek peran. Ini juga menekan prompt dengan `-Force`.

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

### -Paksa
Jangan meminta konfirmasi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

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

### -InputObject
Objek yang mewakili definisi peran yang akan dihapus.

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleDefinition
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, sakelar akan mengembalikan true jika berhasil.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleName
Nama definisi peran yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: RoleDefinitionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Lingkup tempat penetapan peran atau definisi diterapkan, misalnya '/' atau '/keys' atau '/keys/{keyName}'.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleDefinition

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
