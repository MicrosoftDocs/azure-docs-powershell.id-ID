---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvaultroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultRoleDefinition.md
ms.openlocfilehash: 800c1ab164c270fd5d8e34fd7de981c6f528a282
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140000630"
---
# Get-AzKeyVaultRoleDefinition

## SYNOPSIS
Mencantumkan definisi peran HSM terkelola yang diberikan pada lingkup tertentu.

## SYNTAX

### Interaktif (Default)
```
Get-AzKeyVaultRoleDefinition [-HsmName] <String> [-Scope <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### CustomOnly
```
Get-AzKeyVaultRoleDefinition [-HsmName] <String> [-Scope <String>] [-Custom]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzKeyVaultRoleDefinition [-HsmName] <String> [-Scope <String>] -RoleDefinitionName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan definisi peran HSM terkelola yang diberikan pada lingkup tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzKeyVaultRoleDefinition -HsmName myHsm -Scope "/keys"

RoleName                              Description Permissions
--------                              ----------- -----------
Managed HSM Administrator                         1 permission(s)
Managed HSM Crypto Officer                        1 permission(s)
Managed HSM Crypto User                           1 permission(s)
Managed HSM Policy Administrator                  1 permission(s)
Managed HSM Crypto Auditor                        1 permission(s)
Managed HSM Crypto Service Encryption             1 permission(s)
Managed HSM Backup                                1 permission(s)
```

Contoh mencantumkan semua peran di lingkup "/tombol".

### Contoh 2
```powershell
PS C:\> $backupRole = Get-AzKeyVaultRoleDefinition -HsmName myHsm -RoleDefinitionName "Managed HSM Backup User"

PS C:\> $backupRole.Permissions

Actions     NotActions  DataActions NotDataActions
-------     ----------  ----------- --------------
0 action(s) 0 action(s) 3 action(s) 0 action(s)

PS C:\> $backupRole.Permissions.DataActions

Microsoft.KeyVault/managedHsm/backup/start/action
Microsoft.KeyVault/managedHsm/backup/status/action
Microsoft.KeyVault/managedHsm/keys/backup/action
```

Contoh ini mendapatkan peran "Pencadangan HSM terkelola" dan memeriksa izinnya.

### Contoh 3
```powershell
Get-AzKeyVaultRoleDefinition -HsmName myHsm -Custom
```

Contoh ini mencantumkan semua definisi peran kustom menjadi bagian dari "myHsm".

## PARAMETERS

### -Kustom
Jika ditentukan, hanya menampilkan peran kustom yang dibuat dalam direktori.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CustomOnly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -RoleDefinitionName
Nama definisi peran untuk mendapatkan.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: RoleName

Required: True
Position: Named
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleDefinition

## CATATAN

## RELATED LINKS
