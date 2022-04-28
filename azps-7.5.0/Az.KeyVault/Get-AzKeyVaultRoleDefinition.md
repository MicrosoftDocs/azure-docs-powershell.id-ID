---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvaultroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Get-AzKeyVaultRoleDefinition.md
ms.openlocfilehash: d402d690ce14e119fa5ad18ef1d95f6338e83f52
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144213674"
---
# Get-AzKeyVaultRoleDefinition

## SYNOPSIS
Mencantumkan definisi peran dari HSM terkelola tertentu pada cakupan tertentu.

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
Mencantumkan definisi peran dari HSM terkelola tertentu pada cakupan tertentu.

## EXAMPLES

### Contoh 1
```powershell
Get-AzKeyVaultRoleDefinition -HsmName myHsm -Scope "/keys"
```

```output
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

Contohnya mencantumkan semua peran di cakupan "/keys".

### Contoh 2
```powershell
$backupRole = Get-AzKeyVaultRoleDefinition -HsmName myHsm -RoleDefinitionName "Managed HSM Backup User"

$backupRole.Permissions

Actions     NotActions  DataActions NotDataActions
-------     ----------  ----------- --------------
0 action(s) 0 action(s) 3 action(s) 0 action(s)

$backupRole.Permissions.DataActions

Microsoft.KeyVault/managedHsm/backup/start/action
Microsoft.KeyVault/managedHsm/backup/status/action
Microsoft.KeyVault/managedHsm/keys/backup/action
```

Contohnya mendapatkan peran "Cadangan HSM Terkelola" dan memeriksa izinnya.

### Contoh 3
```powershell
Get-AzKeyVaultRoleDefinition -HsmName myHsm -Custom
```

Contoh ini mencantumkan semua definisi peran kustom milik "myHsm".

## PARAMETERS

### -Kustom
Jika ditentukan, hanya menampilkan peran yang dibuat khusus di direktori.

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
Nama definisi peran yang akan didapatkan.

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

### -Cakupan
Cakupan tempat penetapan peran atau definisi berlaku, misalnya, '/' atau '/keys' atau '/keys/{keyName}'.
'/' digunakan saat dihilangkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultRoleDefinition

## NOTES

## RELATED LINKS
