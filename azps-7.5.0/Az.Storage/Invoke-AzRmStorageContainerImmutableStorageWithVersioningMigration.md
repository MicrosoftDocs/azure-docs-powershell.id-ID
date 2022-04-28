---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/invoke-azrmstoragecontainerimmutablestoragewithversioningmigration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration.md
ms.openlocfilehash: cb21a27acdc2bc6f701a90faedae6b8bec29bbc4
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144191528"
---
# Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration

## SYNOPSIS
Migrasikan kontainer blob Storage yang ada untuk mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.

## SYNTAX

### AccountName (Default)
```
Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration [-ResourceGroupName] <String>
 [-StorageAccountName] <String> -Name <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AccountObject
```
Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration -Name <String>
 -StorageAccount <PSStorageAccount> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ContainerObject
```
Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration -InputObject <PSContainer> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration memigrasikan kontainer** blob Storage yang ada untuk mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.
Cmdlet hanya berfungsi ketika akun Storage telah mengaktifkan penerapan versi blob, dan kontainer sudah memiliki ImmutabilityPolicy.

## EXAMPLES

### Contoh 1: Memigrasikan kontainer blob Storage yang ada untuk mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.
```
PS C:\> $t = Invoke-AzRmStorageContainerImmutableStorageWithVersioningMigration -ResourceGroupName "myResourceGroup" -AccountName "mystorageaccount" -Name testcontainer -asjob

PS C:\> $t | Wait-Job
```

Perintah ini memigrasikan kontainer blob Storage yang ada untuk mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.
Perintah hanya berfungsi ketika akun Storage telah mengaktifkan penerapan versi blob, dan kontainer sudah memiliki ImmutabilityPolicy.
Karena perintah biasanya akan berjalan untuk waktu yang lama, Anda dapat menjalankannya secara asinkron dengan '-Asjob'.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -InputObject
Storage objek kontainer

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSContainer
Parameter Sets: ContainerObject
Aliases: Container

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Nama Kontainer

```yaml
Type: System.String
Parameter Sets: AccountName, AccountObject
Aliases: N, ContainerName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
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
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Storage Nama Akun.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases: AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

### Microsoft.Azure.Commands.Management. Storage. Models.PSContainer

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSContainer

## NOTES

## RELATED LINKS
