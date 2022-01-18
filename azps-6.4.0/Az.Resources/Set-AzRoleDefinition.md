---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
ms.assetid: 115A7612-4856-47AE-AEE4-918350CD7009
online version: https://docs.microsoft.com/powershell/module/az.resources/set-azroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Set-AzRoleDefinition.md
ms.openlocfilehash: 9a1c1b829288458967e94cbda8a7ba174fee71bc
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136167381"
---
# Set-AzRoleDefinition

## SYNOPSIS
Memodifikasi peran kustom di Azure RBAC.
Sediakan definisi peran yang dimodifikasi baik sebagai file JSON atau sebagai PSRoleDefinition.
Pertama, gunakan Get-AzRoleDefinition baru untuk mengambil peran kustom yang ingin Anda ubah.
Kemudian, ubah properti yang ingin Anda ubah.
Terakhir, simpan definisi peran menggunakan perintah ini.

## SYNTAX

### InputFileParameterSet
```
Set-AzRoleDefinition -InputFile <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### RoleDefinitionParameterSet
```
Set-AzRoleDefinition -Role <PSRoleDefinition> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzRoleDefinition memperbarui peran kustom yang sudah ada di Azure Role-Based Access Control.
Berikan definisi peran yang diperbarui sebagai input ke perintah sebagai file JSON atau objek PSRoleDefinition.
Definisi peran untuk peran kustom yang diperbarui HARUS berisi Id dan semua properti peran lain yang diperlukan meskipun tidak diperbarui: DisplayName, Deskripsi, Tindakan, AssignableScopes.
NotActions, DataActions, NotDataActions adalah opsional.
Berikut adalah contoh json definisi peran yang diperbarui untuk Set-AzRoleDefinition { "Id": "52a6cc13-ff92-47a8-a39b-2a8205c3087e", "Nama": "Peran yang Diperbarui", "Deskripsi": "Dapat memantau semua sumber daya dan memulai dan memulai ulang mesin virtual", "Tindakan": \[ "*/read", "Microsoft.ClassicCompute/virtualmachines/restart/action", "Microsoft.ClassicCompute/virtualmachines/start/action" \] , "NotActions": \[ "*/write" \] , "DataActions": \[ "Microsoft.Storage /storageAccounts/blobServices/containers/blobs/read" \] , "NotDataActions": \[ "Microsoft.Storage /storageAccounts/blobServices/containers/blobs/write" \] , "AssignableScopes": \[ "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" \] }

## EXAMPLES

### Contoh 1: Perbarui menggunakan PSRoleDefinitionObject
```powershell
PS C:\> $roleDef = Get-AzRoleDefinition "Contoso On-Call"
PS C:\> $roleDef.Actions.Add("Microsoft.ClassicCompute/virtualmachines/start/action")
PS C:\> $roleDef.Description = "Can monitor all resources and start and restart virtual machines"
PS C:\> $roleDef.AssignableScopes = @("/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx")
PS C:\> Set-AzRoleDefinition -Role $roleDef
```

### Contoh 2: Membuat menggunakan file JSON
```powershell
PS C:\> Set-AzRoleDefinition -InputFile C:\Temp\roleDefinition.json
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -InputFile
Nama file yang berisi definisi peran json tunggal yang akan diperbarui.
Hanya menyertakan properti yang akan diperbarui di JSON.
Properti Id diperlukan.

```yaml
Type: System.String
Parameter Sets: InputFileParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Peran
Objek definisi peran yang akan diperbarui

```yaml
Type: Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleDefinition
Parameter Sets: RoleDefinitionParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleDefinition

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleDefinition

## CATATAN
Kata kunci: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

[Get-AzProviderOperation](./Get-AzProviderOperation.md)

[Get-AzRoleDefinition](./Get-AzRoleDefinition.md)

[New-AzRoleDefinition](./New-AzRoleDefinition.md)

[Remove-AzRoleDefinition](./Remove-AzRoleDefinition.md)

