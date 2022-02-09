---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/remove-azkeyvaultroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Remove-AzKeyVaultRoleDefinition.md
ms.openlocfilehash: ff21ddcfec7bbef0be4314f308fee6c00eab2a3a
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138167318"
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
Cmdlet `Remove-AzKeyVaultRoleDefinition` menghapus peran kustom dalam Azure Role-Based Access Control azure KeyVault yang dikelola HSM.
`-RoleName` Menyediakan parameter dari peran kustom atau objek peran yang sudah ada untuk menghapus peran kustom itu.
Secara default, `Remove-AzKeyVaultRoleDefinition` meminta konfirmasi Anda.
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

Contoh ini menghapus peran kustom yang bernama "peran saya" dengan pemipaan objek peran. Perintah juga menyembunyikan perintah oleh `-Force`.

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

### -Force
Jangan minta konfirmasi.

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
Jika sakelar ini ditentukan, maka true akan dikembalikan jika berhasil.

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
Nama definisi peran untuk mendapatkan.

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
Lingkup di mana penetapan peran atau definisi berlaku, misalnya '/' atau '/keys' atau '/keys/{keyName}'.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleDefinition

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
