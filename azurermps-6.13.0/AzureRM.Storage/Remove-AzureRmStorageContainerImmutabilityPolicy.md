---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
Module Name: AzureRM.Storage
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.storage/remove-azurermstoragecontainerimmutabilitypolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Storage/Commands.Management.Storage/help/Remove-AzureRmStorageContainerImmutabilityPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Storage/Commands.Management.Storage/help/Remove-AzureRmStorageContainerImmutabilityPolicy.md
ms.openlocfilehash: 993cc0ec34b5653fb45372b10b32807d6ddd2ce5be37f218453eed8889a77ab2
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140858727"
---
# Remove-AzureRmStorageContainerImmutabilityPolicy

## SYNOPSIS
Menghapus ImmutabilityPolicy wadah Storage blob

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Nama Akun (Default)
```
Remove-AzureRmStorageContainerImmutabilityPolicy [-ResourceGroupName] <String> [-StorageAccountName] <String>
 [-ContainerName] <String> [-Etag] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AccountObject
```
Remove-AzureRmStorageContainerImmutabilityPolicy [-ContainerName] <String> -StorageAccount <PSStorageAccount>
 [-Etag] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ContainerObject
```
Remove-AzureRmStorageContainerImmutabilityPolicy -Container <PSContainer> [-Etag] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ImmutabilityPolicyObject
```
Remove-AzureRmStorageContainerImmutabilityPolicy -InputObject <PSImmutabilityPolicy>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmStorageContainerImmutabilityPolicy** menghapus ImmutabilityPolicy penampung Storage blob.

## EXAMPLES

### Contoh 1: Menghapus ImmutabilityPolicy wadah Storage blob dengan nama Storage dan nama wadah akun
```
PS C:\>$policy = Get-AzureRmStorageContainerImmutabilityPolicy -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount" -ContainerName "myContainer"
PS C:\>Remove-AzureRmStorageContainerImmutabilityPolicy -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount" -ContainerName "myContainer" -Etag $policy.Etag
```

Perintah ini menghapus ImmutabilityPolicy wadah Storage blob dengan Storage dan nama wadah akun.

### Contoh 2: Menghapus ImmutabilityPolicy wadah Storage blob, Storage objek akun
```
PS C:\>$accountObject = Get-AzureRmStorageAccount -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount"
PS C:\>$policy = Get-AzureRmStorageContainerImmutabilityPolicy -StorageAccount $accountObject -ContainerName "myContainer"
PS C:\>Remove-AzureRmStorageContainerImmutabilityPolicy -StorageAccount $accountObject -ContainerName "myContainer" -Etag $policy.Etag
```

Perintah ini menghapus ImmutabilityPolicy pada wadah blob Storage, dengan Storage objek akun. 

### Contoh 3: Menghapus ImmutabilityPolicyof a Storage blob container, with container object
```
PS C:\>$containerObject = Get-AzureRmStorageContainer -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount" -Name "myContainer"
PS C:\>$policy = Get-AzureRmStorageContainerImmutabilityPolicy -Container $containerObject
PS C:\>Remove-AzureRmStorageContainerImmutabilityPolicy -Container $containerObject -Etag $policy.Etag
```

Perintah ini menghapus ImmutabilityPolicy pada wadah Storage blob dengan Storage wadah sel.

### Contoh 4: Menghapus ImmutabilityPolicy wadah Storage blob, dengan objek ImmutabilityPolicy
```
PS C:\>Get-AzureRmStorageContainerImmutabilityPolicy -ResourceGroupName "myResourceGroup" -AccountName "myStorageAccount" -ContainerName "myContainer" | Remove-AzureRmStorageContainerImmutabilityPolicy
```

Perintah ini menghapus ImmutabilityPolicy pada wadah blob Storage, dengan objek ImmutabilityPolicy.

## PARAMETERS

### -Container
Storage wadah objek

```yaml
Type: PSContainer
Parameter Sets: ContainerObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ContainerName
Nama Kontainer

```yaml
Type: String
Parameter Sets: AccountName, AccountObject
Aliases: N

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Etag
Tag kebijakan keterbacaan.

```yaml
Type: String
Parameter Sets: AccountName, AccountObject, ContainerObject
Aliases: IfMatch

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek ImmutabilityPolicy yang akan Dihapus

```yaml
Type: PSImmutabilityPolicy
Parameter Sets: ImmutabilityPolicyObject
Aliases: ImmutabilityPolicy

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: String
Parameter Sets: AccountName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccount
Storage objek akun

```yaml
Type: PSStorageAccount
Parameter Sets: AccountObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Storage Akun.

```yaml
Type: String
Parameter Sets: AccountName
Aliases: AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Microsoft.Azure.Commands.Management. Storage. Models.PSImmutabilityPolicy

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSImmutabilityPolicy

## CATATAN

## RELATED LINKS

