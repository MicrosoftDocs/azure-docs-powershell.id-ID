---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 115A7612-4856-47AE-AEE4-918350CD7009
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/set-azurermroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Set-AzureRmRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Set-AzureRmRoleDefinition.md
ms.openlocfilehash: f0c22f199d19e97f957bc86fbee8d649d30b622d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142724608"
---
# Set-AzureRmRoleDefinition

## SYNOPSIS
Mengubah peran kustom di Azure RBAC.
Berikan definisi peran yang dimodifikasi baik sebagai file JSON atau sebagai PSRoleDefinition.
Pertama, gunakan perintah Get-AzureRmRoleDefinition untuk mengambil peran kustom yang ingin Anda ubah.
Lalu, ubah properti yang ingin Anda ubah.
Terakhir, simpan definisi peran menggunakan perintah ini.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### InputFileParameterSet
```
Set-AzureRmRoleDefinition -InputFile <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### RoleDefinitionParameterSet
```
Set-AzureRmRoleDefinition -Role <PSRoleDefinition> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzureRmRoleDefinition memperbarui peran kustom yang sudah ada di Azure Role-Based Access Control.
Berikan definisi peran yang diperbarui sebagai input ke perintah sebagai file JSON atau objek PSRoleDefinition.
Definisi peran untuk peran kustom yang diperbarui HARUS berisi Id dan semua properti peran lain yang diperlukan meskipun tidak diperbarui: NamaPajangan, Deskripsi, Tindakan, AssignableScopes.
NotActions, DataActions, NotDataActions bersifat opsional.
Berikut adalah contoh definisi peran yang diperbarui untuk Set-AzureRmRoleDefinition { "Id": "52a6cc13-ff92-47a8-a39b-2a8205c3087e", "Nama": "Peran Diperbarui", "Deskripsi": "Dapat memantau semua sumber daya dan memulai dan memulai ulang mesin virtual", "Tindakan": \[ "*/baca", "Microsoft.ClassicCompute/virtualmachines/restart/action", "Microsoft.ClassicCompute/virtualmachines/start/action" \], "NotActions": \[ "*/write" \], "DataActions": \[ "Microsoft.Storage /storageAccounts/blobServices/containers/blobs/read" \], "NotDataActions": \[ "Microsoft.Storage /storageAccounts/blobServices/containers/blobs/write" \], "AssignableScopes": \["/subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxx"\] }

## EXAMPLES

### Memperbarui menggunakan PSRoleDefinitionObject
```
PS C:\> $roleDef = Get-AzureRmRoleDefinition "Contoso On-Call"
          PS C:\> $roleDef.Actions.Add("Microsoft.ClassicCompute/virtualmachines/start/action")
          PS C:\> $roleDef.Description = "Can monitor all resources and start and restart virtual machines"
          PS C:\> $roleDef.AssignableScopes = @("/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx")

          PS C:\> Set-AzureRmRoleDefinition -Role $roleDef
```

### Membuat menggunakan file JSON
```
PS C:\> Set-AzureRmRoleDefinition -InputFile C:\Temp\roleDefinition.json
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputFile
Nama file yang berisi definisi peran json tunggal yang akan diperbarui.
Hanya menyertakan properti yang akan diperbarui dalam JSON.
Properti Id Diperlukan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleDefinition
Parameter: Peran (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.Authorization.PSRoleDefinition

## NOTES
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, sumber daya, grup, Templat, penyebaran

## RELATED LINKS

[Get-AzureRmProviderOperation](./Get-AzureRmProviderOperation.md)

[Get-AzureRmRoleDefinition](./Get-AzureRmRoleDefinition.md)

[AzureRmRoleDefinition Baru](./New-AzureRmRoleDefinition.md)

[Hapus-AzureRmRoleDefinition](./Remove-AzureRmRoleDefinition.md)

